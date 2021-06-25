FROM ubuntu
RUN rm -f /etc/apt/apt.conf.d/docker-clean; echo 'Binary::apt::APT::Keep-Downloaded-Packages "true";' > /etc/apt/apt.conf.d/keep-cache
COPY . .
RUN --mount=type=cache,target=/var/cache/apt --mount=type=cache,target=/var/lib/apt \
  apt update && apt-get --no-install-recommends install -y gcc