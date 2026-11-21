# Railway-Apps booking microservice
# SPDX-License-Identifier: Apache-2.0 · Keep this notice and the NOTICE file in any copy or derivative work.
#
# preferences — Node.js microservice (zero npm dependencies). Build from the repo root:
#   docker build -f services/preferences/Dockerfile -t railway-apps-preferences .
FROM node:22-alpine
LABEL org.opencontainers.image.title="railway-apps-preferences" \
      org.opencontainers.image.description="Railway-Apps preferences microservice" \
      org.opencontainers.image.licenses="Apache-2.0" \
      org.opencontainers.image.source="https://github.com/grlokesh96/Railway-Apps"
WORKDIR /app
ENV NODE_ENV=production NODE_PATH=/app/lib
COPY NOTICE ./NOTICE
COPY libs/nodekit ./lib
COPY services/preferences/ ./
USER node
EXPOSE 8080
CMD ["node", "index.js"]
