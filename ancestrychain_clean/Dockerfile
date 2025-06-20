# ---------- Builder stage ----------
FROM node:18-alpine AS builder
WORKDIR /app

# Install dependencies based on lock files
COPY package*.json ./
RUN npm ci --ignore-scripts

# Copy source and build the Next.js app (standalone output)
COPY . .
RUN npm run build

# ---------- Runner stage ----------
FROM node:18-alpine AS runner
WORKDIR /app

ARG NODE_ENV=production
ENV NODE_ENV=${NODE_ENV} \
    PORT=3000 \
    NEXT_TELEMETRY_DISABLED=1

# Create an unprivileged user for security
RUN addgroup -g 1001 nextjs && adduser -u 1001 -G nextjs -s /bin/sh -D nextjs
USER nextjs

# Copy minimal artefacts from the builder
COPY --from=builder /app/public ./public
COPY --from=builder /app/.next/standalone ./
COPY --from=builder /app/.next/static ./.next/static

EXPOSE 3000
CMD ["node", "server.js"]
