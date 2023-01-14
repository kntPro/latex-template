FROM ubuntu:22.04

ENV DEBIAN_FRONTEND noninteractive

ENV UID $(id -u)
ENV GID $(id -g)

# install general packages
RUN apt-get update && \
  apt-get install -y --no-install-recommends \
    build-essential \
    cpanminus \
    git \
    curl \
    wget \
    locales \
    libfontconfig1 \
    ca-certificates && \
  apt-get clean -y && \
  apt-get autoremove -y && \
  apt-get autoclean -y && \
  rm -rf /var/lib/apt/lists/*

# install texlive
# note: 
ARG TEXLIVE_URL="http://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz"
ARG TEXLIVE_VERSION="2022"

WORKDIR /tmp/install-tl-unx
RUN wget -nv ${TEXLIVE_URL} && \
  tar -zxf ./install-tl-unx.tar.gz --strip-components=1 && \
  /bin/echo -e 'selected_scheme scheme-basic\ntlpdbopt_install_docfiles 0\ntlpdbopt_install_srcfiles 0' \
  > ./texlive.profile && \
  ./install-tl --profile=./texlive.profile && \
  rm -rf /tmp/install-tl-unx

ENV PATH /usr/local/texlive/${TEXLIVE_VERSION}/bin/x86_64-linux:$PATH

RUN tlmgr update --self --all && tlmgr install \
  collection-basic \
  collection-latexrecommended \
  collection-xetex \
  collection-bibtexextra \
  collection-binextra \
  collection-fontsrecommended \
  collection-langenglish \
  collection-langjapanese \
  collection-pictures \
  collection-mathscience \
  beamer \
  latexmk \
  latexindent
COPY .latexmkrc /root

# install perl package for latexindent
RUN cpanm Log::Log4perl

WORKDIR /workdir

CMD [ "bash" ]