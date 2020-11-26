FROM ubuntu:18.04
ENV DEBIAN_FRONTEND noninteractive
RUN apt update && apt upgrade -y
RUN apt install -y git curl locales python3 npm node-gyp build-essential python3-dev python3-pip \
    python3-setuptools python3-wheel python3-cffi libcairo2 libpango-1.0-0 libpangocairo-1.0-0 \
    libgdk-pixbuf2.0-0 libffi-dev shared-mime-info chromium-browser
RUN pip3 install mkdocs-material WeasyPrint mkdocs && \
    pip3 install -e git+https://github.com/jwaschkau/mkpdfs-mkdocs-plugin.git#egg=mkpdfs-mkdocs-plugin && \
    pip3 install mkdocs-with-pdf
RUN npm i -g node-sass@4.14.1 request@2.88.2 har-validator@5.1.5
RUN cd src/mkpdfs-mkdocs-plugin/mkpdfs_mkdocs/design && npm i && npm i modularscale-sass --save-dev
RUN cd src/mkpdfs-mkdocs-plugin/mkpdfs_mkdocs/design && node-sass report.scss report.css
RUN cd src/mkpdfs-mkdocs-plugin && python3 setup.py install
ENV LC_ALL=C.UTF-8
ENV LANG=C.UTF-8
RUN dpkg-reconfigure locales
