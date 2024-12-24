# Copied from https://github.com/prenone/platformio-vscode-devcontainer
ARG VARIANT=bookworm
FROM mcr.microsoft.com/vscode/devcontainers/base:${VARIANT}

ENV DEBIAN_FRONTEND=noninteractive
RUN sudo apt-get update \
  && sudo apt-get -y install --no-install-recommends \
  clang \
  udev

ARG FEDORA_COMPAT=0
### Set up compatibility with Fedora host (if needed)
### Since Fedora uses `18` as the group for dialout, we need to add it to the container
RUN if [ "$FEDORA_COMPAT" = "1" ]; then \
  sudo groupadd -g 18 compat_dialout; \
  sudo usermod -a -G compat_dialout vscode; \
  fi
