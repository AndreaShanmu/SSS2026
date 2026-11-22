FROM node:20-alpine AS builder
RUN apk add --no-cache git
RUN git clone https://github.com/AndreaShanmu/SSS2026.git /repo
WORKDIR /repo/SomeBankingApp/frontend
RUN npm ci
RUN npm run build

FROM nginx:alpine-slim
WORKDIR /usr/share/nginx/html
COPY --from=builder /repo/SomeBankingApp/frontend/dist/SomeBankingFrontend/browser .
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]