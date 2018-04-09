FROM xuanwen/ubuntu:latest

MAINTAINER hosea,<Ghan6373@163.com>

RUN \
    apt-get update && \
    apt-get install -y git curl vim-gtk tree net-tools && \
    apt-get install -y nodejs npm && \
    apt-get clean  && \
    ln -s /usr/bin/nodejs  /usr/bin/node  && \
    alias cnpm="npm --registry=https://registry.npm.taobao.org --cache=$HOME/.npm/.cache/cnpm --disturl=https://npm.taobao.org/dist \
    --userconfig=$HOME/.cnpmrc"  && \
    npm install hexo-cli -g && \
    npm install -g n && \
    n stable
ENV LANG C.UTF-8

WORKDIR /Hexo
#VOLUME ["/Hexo/source", "/Hexo/themes", "/root/.ssh"]
RUN \
    hexo init && \
    npm install hexo --save && \
EXPOSE 4000
CMD ['/bin/bash']
