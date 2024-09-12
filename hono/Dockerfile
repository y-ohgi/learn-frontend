FROM node:22-slim AS base

# === builder ===
FROM base AS builder

WORKDIR /app

COPY package* .

RUN npm install

COPY . .

# === runner ===
FROM base AS runner

WORKDIR /app

COPY --from=builder --chown=node:node /app/package* .
COPY --from=builder --chown=node:node /app/node_modules ./node_modules

COPY --chown=node:node . .

USER node

EXPOSE 8787

CMD ["npm", "run", "dev"]
