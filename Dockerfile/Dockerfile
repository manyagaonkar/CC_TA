FROM jenkins/jenkins:lts

# Switch to root for installation
USER root

# Set reliable mirrors, clear cache, and ensure dependencies are installed
RUN apt-get clean && \
    apt-get update -o Acquire::ForceIPv4=true && \
    apt-get install -y --no-install-recommends \
    make \
    g++ \
    ca-certificates \
    apt-transport-https \
    gnupg \
    && rm -rf /var/lib/apt/lists/*

# Ensure Jenkins user permissions (good practice)
RUN chown -R jenkins:jenkins /var/jenkins_home

# Switch back to Jenkins user
USER jenkins
