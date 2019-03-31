From docker/java

ENV GRADLE_FILENAME gradle-5.0
ENV GRADLE_URL https://services.gradle.org/distributions/${GRADLE_FILENAME}-bin.zip
ENV GRADLE_HOME /opt/gradle/${GRADLE_FILENAME}
ENV PATH ${PATH}:${GRADLE_HOME}/bin
RUN cd /opt && \
    apt-get update -y && \
    apt-get install -y unzip && \
    wget -q ${GRADLE_URL} && \
    unzip gradle-*.zip -d gradle && \
    apt-get clean && \
    gradle -v