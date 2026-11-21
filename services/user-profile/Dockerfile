# Railway-Apps · 50 Microservices Project by DevOps Shack
# Copyright (c) 2026 DevOps Shack (Aditya Jaiswal) · https://devopsshack.com · https://www.youtube.com/@devopsshack
# SPDX-License-Identifier: Apache-2.0 · Keep this notice and the NOTICE file in any copy or derivative work.
#
# user-profile — Node.js microservice (zero npm dependencies). Build from the repo root:
#   docker build -f services/user-profile/Dockerfile -t railway-apps-user-profile .
FROM node:22-alpine
LABEL org.opencontainers.image.title="railway-apps-user-profile" \
      org.opencontainers.image.description="Railway-Apps user-profile microservice · 50 Microservices Project by DevOps Shack" \
      org.opencontainers.image.vendor="DevOps Shack" \
      org.opencontainers.image.authors="DevOps Shack <office@devopsshack.com>" \
      org.opencontainers.image.url="https://devopsshack.com" \
      org.opencontainers.image.source="https://github.com/jaiswaladi246/50-MicroServices-Project-By-DevOpsShack" \
      org.opencontainers.image.documentation="https://www.youtube.com/@devopsshack" \
      org.opencontainers.image.licenses="Apache-2.0" \
      com.devopsshack.project="Railway-Apps - 50 Microservices Project by DevOps Shack"
WORKDIR /app
ENV NODE_ENV=production NODE_PATH=/app/lib
COPY NOTICE ./NOTICE
COPY libs/nodekit ./lib
COPY services/user-profile/ ./
USER node
EXPOSE 8080
CMD ["node", "index.js"]
