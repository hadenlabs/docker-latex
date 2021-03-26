FROM ubuntu:18.04

ENV DEBIAN_FRONTEND noninteractive

ENV RUNTIME_DEPS  \
    biber \
    build-essential \
    cabextract \
    fontconfig \
    fonts-freefont-otf \
    fonts-freefont-ttf \
    fonts-linuxlibertine \
    fonts-inconsolata\
    fonts-oflb-asana-math \
    fonts-roboto \
    fonts-roboto-fontface \
    graphviz \
    latexmk \
    libimage-exiftool-perl \
    tex-gyre \
    texlive-bibtex-extra \
    texlive-fonts-extra \
    texlive-fonts-recommended \
    texlive-full \
    texlive-generic-extra \
    texlive-generic-recommended \
    texlive-lang-english \
    texlive-latex-base \
    texlive-latex-extra \
    texlive-latex-recommended \
    texlive-luatex \
    texlive-xetex \
    xfonts-utils \
    texlive

ENV BUILD_DEPS curl \
    make \
    git

RUN apt-get update -y \
  && apt-get install -y --no-install-recommends --no-install-suggests $BUILD_DEPS $RUNTIME_DEPS \
  && apt-get clean autoclean \
  && apt-get purge -y --auto-remove $BUILD_DEPS \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Define default command.
ENTRYPOINT ["xelatex"]

WORKDIR /root
