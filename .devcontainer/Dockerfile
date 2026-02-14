FROM mcr.microsoft.com/devcontainers/base:ubuntu-22.04

# Install Flutter and dependencies
RUN apt-get update && \
    apt-get install -y \
    curl \
    git \
    unzip \
    xz-utils \
    zip \
    libglu1-mesa \
    openjdk-17-jdk \
    && rm -rf /var/lib/apt/lists/*

# Install Flutter
RUN git clone https://github.com/flutter/flutter.git /opt/flutter -b stable
ENV PATH="/opt/flutter/bin:/opt/flutter/bin/cache/dart-sdk/bin:${PATH}"

# Accept Android SDK licenses
RUN yes | flutter doctor --android-licenses || true

# Run flutter doctor to verify installation
RUN flutter doctor