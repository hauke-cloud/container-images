FROM quay.io/coreos-assembler/coreos-assembler:v0.17.0

LABEL org.opencontainers.image.source="https://github.com/hauke-cloud/actions-runner-cosa"
LABEL org.opencontainers.image.description="A Github ARC runner image based on CoreOS Assembler"

ARG RUNNER_VERSION="2.319.1"
ARG RUNNER_ARCH="x64"
ARG RUNNER_CONTAINER_HOOKS_VERSION="0.6.1"

USER root

# Fullfill dotnet dependencies
RUN dnf install -y dotnet-runtime-6.0 \
  && dnf clean all

## Add runner user
RUN adduser --uid 1001 runner \
  && groupadd docker --gid 123 \
  && usermod -aG docker runner \
  && echo "runner ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

# Modify builder user
RUN usermod -aG docker builder \
  && echo "builder ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

WORKDIR /home/runner

RUN curl -f -L -o runner.tar.gz https://github.com/actions/runner/releases/download/v${RUNNER_VERSION}/actions-runner-linux-${RUNNER_ARCH}-${RUNNER_VERSION}.tar.gz \
  && tar xzf ./runner.tar.gz \
  && rm runner.tar.gz

RUN curl -f -L -o runner-container-hooks.zip https://github.com/actions/runner-container-hooks/releases/download/v${RUNNER_CONTAINER_HOOKS_VERSION}/actions-runner-hooks-k8s-${RUNNER_CONTAINER_HOOKS_VERSION}.zip \
  && unzip ./runner-container-hooks.zip -d ./k8s \
  && rm runner-container-hooks.zip

USER runner
