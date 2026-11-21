# Railway-Apps booking microservice
# SPDX-License-Identifier: Apache-2.0 · Keep this notice and the NOTICE file in any copy or derivative work.
#
# tourism — Node.js microservice (zero npm dependencies). Build from the repo root:
#   docker build -f services/tourism/Dockerfile -t railway-apps-tourism .
FROM node:22-alpine
LABEL org.opencontainers.image.title="railway-apps-tourism" \
      org.opencontainers.image.description="Railway-Apps tourism microservice" \
      org.opencontainers.image.licenses="Apache-2.0" \
      org.opencontainers.image.source="https://github.com/grlokesh96/Railway-Apps"
WORKDIR /app
ENV NODE_ENV=production NODE_PATH=/app/lib
COPY NOTICE ./NOTICE
COPY libs/nodekit ./lib
COPY services/tourism/ ./
USER node
EXPOSE 8080
CMD ["node", "index.js"]
