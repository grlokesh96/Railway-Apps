# Railway-Apps booking microservice
# SPDX-License-Identifier: Apache-2.0 · Keep this notice and the NOTICE file in any copy or derivative work.
#
# ticket-pdf — Python microservice (standard library only). Build from the repo root:
#   docker build -f services/ticket-pdf/Dockerfile -t railway-apps-ticket-pdf .
FROM python:3.13-alpine
LABEL org.opencontainers.image.title="railway-apps-ticket-pdf" \
      org.opencontainers.image.description="Railway-Apps ticket-pdf microservice" \
      org.opencontainers.image.licenses="Apache-2.0" \
      org.opencontainers.image.source="https://github.com/grlokesh96/Railway-Apps"
WORKDIR /app
ENV PYTHONPATH=/app/lib PYTHONUNBUFFERED=1 PYTHONDONTWRITEBYTECODE=1
COPY NOTICE ./NOTICE
COPY libs/pykit ./lib
COPY services/ticket-pdf/app.py ./
USER 1000:1000
EXPOSE 8080
CMD ["python", "app.py"]
