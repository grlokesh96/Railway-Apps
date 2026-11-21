# Railway-Apps booking microservice
# SPDX-License-Identifier: Apache-2.0 · Keep this notice and the NOTICE file in any copy or derivative work.
#
# frontend — Node.js microservice (zero npm dependencies). Build from the repo root:
#   docker build -f services/frontend/Dockerfile -t railway-apps-frontend .
FROM node:22-alpine
LABEL org.opencontainers.image.title="railway-apps-frontend" \
      org.opencontainers.image.description="Railway-Apps frontend microservice" \
      org.opencontainers.image.licenses="Apache-2.0" \
      org.opencontainers.image.source="https://github.com/grlokesh96/Railway-Apps"
WORKDIR /app
ENV NODE_ENV=production NODE_PATH=/app/lib
COPY NOTICE ./NOTICE
COPY libs/nodekit ./lib
COPY services.json ./services.json
COPY services/frontend/ ./
USER node
EXPOSE 8080
CMD ["node", "index.js"]
