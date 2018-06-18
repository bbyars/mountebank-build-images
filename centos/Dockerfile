FROM centos:7.5.1804

LABEL maintainer Brandon Byars <brandon.byars@gmail.com>

RUN curl --silent --location https://rpm.nodesource.com/setup_8.x | bash - \
    && yum -y install nodejs gcc ruby-devel make rpm-build libffi-devel wget sudo \
    && gem install bundler --no-ri --no-rdoc \
    && useradd -ms /bin/bash developer \
    && echo 'ALL            ALL = (ALL) NOPASSWD: ALL' | sudo EDITOR='tee -a' visudo

USER developer

ENV PATH="${PATH}:/home/developer/bin"
