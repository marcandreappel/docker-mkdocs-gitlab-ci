FROM debian:buster
ENV DEBIAN_FRONTEND noninteractive
ENV LC_ALL=C.UTF-8
RUN apt update
RUN apt install -y git curl locales chromium rsync openssh-client build-essential python3-dev python3-pip python3-setuptools python3-wheel python3-cffi libcairo2 libpango-1.0-0 libpangocairo-1.0-0 libgdk-pixbuf2.0-0 libffi-dev shared-mime-info
RUN pip3 install --no-cache-dir WeasyPrint mkdocs mkdocs-with-pdf mkdocs-material
RUN dpkg-reconfigure locales
RUN apt autoremove -y && apt clean -y
