FROM docker/cordova/nodejs:8.0.0

# Installs Cordova
ENV PATH ${PATH}:${ANDROID_HOME}/tools/bin
ENV CORDOVA_VERSION 8.1.2
RUN npm install -g npm && \
    node --version && \
    npm install -g cordova@{CORDOVA_VERSION}

VOLUME ["/data"]
WORKDIR /data
