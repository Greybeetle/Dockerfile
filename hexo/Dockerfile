FROM centos:7
ENV LANG C.UTF-8
LABEL author=hosea email=Ghan6373@163.com
WORKDIR /opt/hexo
RUN yum install -y epel-release && \
yum install -y nodejs && npm config set registry https://registry.npm.taobao.org \
&& npm install hexo-cli -g && hexo init hosea && cd hosea && npm install \
&& yum install git
WORKDIR hosea
EXPOSE 4000
ENTRYPOINT ["hexo","server"]
