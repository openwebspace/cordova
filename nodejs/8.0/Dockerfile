From docker/android:25.0.3

# Installs i386 architecture required for running 32 bit Android tools
RUN apt-get update -y && \
    apt-get install -y curl && \
    curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash - && \
    sudo apt-get install -y nodejs && \
    apt-get clean && \
    node --version