FROM balenalib/aarch64-debian

RUN install_packages dnsmasq wireless-tools

WORKDIR /usr/src/app

ARG VERSION="4.4.6"
RUN curl -Ls "https://github.com/balena-io/wifi-connect/releases/download/v$VERSION/wifi-connect-v$VERSION-linux-aarch64.tar.gz" \
  | tar -xvz -C  /usr/src/app/

COPY logo.svg /usr/src/app/ui/static/media/logo.34c0c94e.svg
COPY start.sh .

CMD ["bash", "start.sh"]