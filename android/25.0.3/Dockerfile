FROM docker/gradle:5.0.0

# Installs i386 architecture required for running 32 bit Android tools
RUN apt-get update -y && \
    apt-get install -y libc6-dev-i386 lib32z1 && \
    apt-get clean

# Installs Android SDK
ENV ANDROID_SDK_FILENAME sdk-tools-linux-4333796.zip
ENV ANDROID_SDK_URL https://dl.google.com/android/repository/${ANDROID_SDK_FILENAME}
ENV ANDROID_API_LEVEL 27
ENV ANDROID_BUILD_TOOLS_VERSION 25.0.3
ENV ANDROID_HOME /opt/android
ENV PATH ${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/tools/bin:${ANDROID_HOME}/platform-tools
RUN cd /opt && \
    wget -q ${ANDROID_SDK_URL} && \
    apt-get install -y unzip && \
    unzip ${ANDROID_SDK_FILENAME} -d android && \
    rm ${ANDROID_SDK_FILENAME} && \
    yes | ${ANDROID_HOME}/tools/bin/sdkmanager --licenses && \
    ${ANDROID_HOME}/tools/bin/sdkmanager  "tools" "platforms;android-${ANDROID_API_LEVEL}" "platform-tools" "build-tools;${ANDROID_BUILD_TOOLS_VERSION}" && \
    ${ANDROID_HOME}/tools/bin/sdkmanager --list
