FROM node:16 AS builder

# Create app directory
WORKDIR /app

RUN corepack enable

ADD package.json pnpm-lock.yaml ./

RUN --mount=type=cache,id=pnpm-store,target=/root/.pnpm-store \
    pnpm install --frozen-lockfile

ADD . .

EXPOSE 3000
CMD [ "npm", "run", "start" ]