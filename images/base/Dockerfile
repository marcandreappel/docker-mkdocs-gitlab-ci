FROM debian:stretch-slim
ENV DEBIAN_FRONTEND noninteractive
ENV LC_ALL=C.UTF-8
RUN apt update && apt install -y git curl locales python3 build-essential python3-dev python3-pip libcairo2 libpango-1.0-0 libpangocairo-1.0-0 libgdk-pixbuf2.0-0 libffi-dev shared-mime-info chromium && pip3 install --no-cache-dir mkdocs-material WeasyPrint mkdocs mkdocs-with-pdf && dpkg-reconfigure locales && apt autoremove -y && apt clean -y
