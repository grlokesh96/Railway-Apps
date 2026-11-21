# Railway-Apps booking microservice
# SPDX-License-Identifier: Apache-2.0 · Keep this notice and the NOTICE file in any copy or derivative work.
#
# kyc — Python microservice (standard library only). Build from the repo root:
#   docker build -f services/kyc/Dockerfile -t railway-apps-kyc .
FROM python:3.13-alpine
LABEL org.opencontainers.image.title="railway-apps-kyc" \
      org.opencontainers.image.description="Railway-Apps kyc microservice" \
      org.opencontainers.image.licenses="Apache-2.0" \
      org.opencontainers.image.source="https://github.com/grlokesh96/Railway-Apps"
WORKDIR /app
ENV PYTHONPATH=/app/lib PYTHONUNBUFFERED=1 PYTHONDONTWRITEBYTECODE=1
COPY NOTICE ./NOTICE
COPY libs/pykit ./lib
COPY services/kyc/app.py ./
USER 1000:1000
EXPOSE 8080
CMD ["python", "app.py"]
