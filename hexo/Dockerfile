FROM xuanwen/ubuntu:latest

MAINTAINER hosea,<Ghan6373@163.com>

RUN \
    apt-get update && \
    apt-get install -y git curl vim-gtk tree net-tools && \
    apt-get install -y nodejs npm && \
    apt-get -y upgrade && \
    apt-get clean  && \
    ln -s /usr/bin/nodejs  /usr/bin/node  && \
    alias cnpm="npm --registry=https://registry.npm.taobao.org --cache=$HOME/.npm/.cache/cnpm --disturl=https://npm.taobao.org/dist \
    --userconfig=$HOME/.cnpmrc"  && \
    npm install hexo-cli -g
ENV LANG C.UTF-8

WORKDIR /Hexo
RUN \
    npm install -g n && \
    n stable && \
    hexo init && \
    npm install hexo-deployer-git --save && \

    # _config.yml配置文件
    mkdir -p /root/hexo_files && \
    git clone -b hexo_theme git@github.com:lovewen/lovewen.github.io.git /root/hexo_files && \
    cp /root/hexo_files/lovewen.github.io.git/landscape/* . && \
    rm -r /root/*

EXPOSE 4000
CMD ['/bin/bash']
