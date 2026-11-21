# Railway-Apps booking microservice
# SPDX-License-Identifier: Apache-2.0 · Keep this notice and the NOTICE file in any copy or derivative work.
#
# wallet — Go microservice. Build from the repo root:
#   docker build -f services/wallet/Dockerfile -t railway-apps-wallet .
# Cross-compiles on the build machine, so amd64 and arm64 images build fast without emulation.
FROM --platform=$BUILDPLATFORM golang:1.24-alpine AS build
ARG TARGETOS TARGETARCH
WORKDIR /src
COPY libs/gokit ./libs/gokit
COPY services/wallet ./services/wallet
WORKDIR /src/services/wallet
RUN CGO_ENABLED=0 GOOS=$TARGETOS GOARCH=$TARGETARCH go build -trimpath -ldflags="-s -w" -o /out/app .

FROM gcr.io/distroless/static-debian12:nonroot
LABEL org.opencontainers.image.title="railway-apps-wallet" \
      org.opencontainers.image.description="Railway-Apps wallet microservice" \
      org.opencontainers.image.licenses="Apache-2.0" \
      org.opencontainers.image.source="https://github.com/grlokesh96/Railway-Apps"
COPY NOTICE /NOTICE
COPY --from=build /out/app /app
USER nonroot:nonroot
EXPOSE 8080
ENTRYPOINT ["/app"]
