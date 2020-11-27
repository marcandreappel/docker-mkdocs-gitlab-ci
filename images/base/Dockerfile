FROM ubuntu:20.04
ENV DEBIAN_FRONTEND noninteractive
RUN apt update && apt upgrade -y
RUN apt install -y git curl locales python3 build-essential python3-dev python3-pip \
    python3-setuptools python3-wheel python3-cffi libcairo2 libpango-1.0-0 libpangocairo-1.0-0 \
    libgdk-pixbuf2.0-0 libffi-dev shared-mime-info chromium-browser
RUN pip3 install mkdocs-material WeasyPrint mkdocs mkdocs-with-pdf
ENV LC_ALL=C.UTF-8
RUN dpkg-reconfigure locales
