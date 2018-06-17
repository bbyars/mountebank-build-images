FROM centos:7.5.1804

LABEL maintainer Brandon Byars <brandon.byars@gmail.com>

RUN curl --silent --location https://rpm.nodesource.com/setup_8.x | bash - \
    && yum -y install nodejs gcc ruby-devel make rpm-build libffi-devel wget \
    && gem install bundler --no-ri --no-rdoc \
    && useradd -ms /bin/bash developer

USER developer

RUN PATH=$PATH:/home/developer/bin  # not sure why rubygems doesn't do this when it installs
