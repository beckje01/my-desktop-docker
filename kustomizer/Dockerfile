FROM alpine:latest
RUN apk add curl git openssh \
  && git config --global url.ssh://git@github.com/.insteadOf https://github.com/
RUN  curl -L --output /tmp/kustomize_v3.5.5_linux_amd64.tar.gz https://github.com/kubernetes-sigs/kustomize/releases/download/kustomize%2Fv3.5.5/kustomize_v3.5.5_linux_amd64.tar.gz \
  && echo "23306e0c0fb24f5a9fea4c3b794bef39211c580e4cbaee9e21b9891cb52e73e7  /tmp/kustomize_v3.5.5_linux_amd64.tar.gz" | sha256sum -c \
  && tar -xvzf /tmp/kustomize_v3.5.5_linux_amd64.tar.gz -C /usr/local/bin \
  && chmod +x /usr/local/bin/kustomize
WORKDIR /kustomize
ENTRYPOINT ["kustomize"]
