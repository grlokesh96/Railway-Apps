# Railway-Apps booking microservice
# SPDX-License-Identifier: Apache-2.0 · Keep this notice and the NOTICE file in any copy or derivative work.
#
# invoices — Java 21 microservice (JDK only, no framework). Build from the repo root:
#   docker build -f services/invoices/Dockerfile -t railway-apps-invoices .
# Bytecode is platform-independent, so it compiles once on the build machine.
FROM --platform=$BUILDPLATFORM eclipse-temurin:21-jdk-alpine AS build
WORKDIR /src
COPY libs/javakit/Kit.java services/invoices/Main.java ./
RUN javac -d /out Kit.java Main.java

FROM eclipse-temurin:21-jre
LABEL org.opencontainers.image.title="railway-apps-invoices" \
      org.opencontainers.image.description="Railway-Apps invoices microservice" \
      org.opencontainers.image.licenses="Apache-2.0" \
      org.opencontainers.image.source="https://github.com/grlokesh96/Railway-Apps"
WORKDIR /app
COPY NOTICE ./NOTICE
COPY --from=build /out ./
USER 1000:1000
EXPOSE 8080
ENTRYPOINT ["java", "-XX:MaxRAMPercentage=75", "-XX:+UseSerialGC", "-cp", "/app", "Main"]
