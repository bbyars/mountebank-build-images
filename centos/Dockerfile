FROM centos:7.5.1804

LABEL maintainer Brandon Byars <brandon.byars@gmail.com>

RUN curl --silent --location https://rpm.nodesource.com/setup_8.x | bash - \
    && yum -y install nodejs gcc gcc-c++ ruby-devel make libffi-devel \
    && gem install bundler --no-ri --no-rdoc \
    && useradd -ms /bin/bash developer

USER developer
