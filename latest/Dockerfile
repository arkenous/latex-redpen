## -*- docker-image-name: "trileg/latex-redpen" -*-
FROM trileg/arch-base:latest
MAINTAINER Kensuke Kosaka <kosaka@trileg.net>

# Install packages
RUN pacman -Syu --noconfirm texlive-langcjk texlive-fontsextra jdk8-openjdk git openssh &> /dev/null

# Run below command to resolve dvipdfmx mktexpk font error
RUN updmap &> /dev/null

# Install RedPen
RUN curl --silent -L -o /tmp/redpen.tar.gz https://github.com/redpen-cc/redpen/releases/download/redpen-1.7.6/redpen-1.7.6.tar.gz && \
  mkdir /root/redpen && \
  tar -zxvf /tmp/redpen.tar.gz -C /root/redpen --strip-components 1 > /dev/null && \
  rm -f /tmp/redpen.tar.gz

ENV PATH /root/redpen/bin:$PATH

RUN pacman -Scc --noconfirm &> /dev/null
