FROM ubuntu:16.04

RUN apt-get update && \
    apt-get -y install sudo

# Install gosu
RUN curl -o /usr/local/bin/gosu -fsSL \
    "https://github.com/tianon/gosu/releases/download/1.7/gosu-$(dpkg --print-architecture)" && \
    chmod +x /usr/local/bin/gosu

# Create user "jenkins"
RUN id jenkins 2>/dev/null || useradd --uid 1000 --create-home jenkins

# EOF
