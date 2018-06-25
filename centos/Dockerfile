FROM centos:7.5.1804

LABEL maintainer Brandon Byars <brandon.byars@gmail.com>

RUN curl --silent --location https://rpm.nodesource.com/setup_8.x | bash - \
    && yum -y install nodejs gcc make rpm-build libffi-devel wget sudo which openssl zlib-devel openssl-devel \
    && yum -y groupinstall "Development Tools" \
    && useradd -ms /bin/bash developer \
    && echo 'ALL            ALL = (ALL) NOPASSWD: ALL' | sudo EDITOR='tee -a' visudo

WORKDIR /tmp/

# https://www.ruby-lang.org/en/downloads/
RUN curl https://cache.ruby-lang.org/pub/ruby/2.4/ruby-2.4.4.tar.gz -o /tmp/ruby-2.4.4.tar.gz \
    && echo "254f1c1a79e4cc814d1e7320bc5bdd995dc57e08727d30a767664619a9c8ae5a /tmp/ruby-2.4.4.tar.gz" > /tmp/ruby-2.4.4-sha256sum \
    && sha256sum -c /tmp/ruby-2.4.4-sha256sum \
    && tar xf /tmp/ruby-2.4.4.tar.gz \
    && /tmp/ruby-2.4.4/configure \
    && make \
    && make install \
    && gem install bundler --no-ri --no-rdoc \
    && rm -rf /tmp/*

USER developer
