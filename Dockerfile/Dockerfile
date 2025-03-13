FROM jenkins/jenkins:lts

# Switch to root for installation
USER root

# Fix networking issues, add reliable sources, and install dependencies
RUN apt-get clean && \
    apt-get update -o Acquire::ForceIPv4=true && \
    apt-get install -y --no-install-recommends \
    make \
    g++ \
    apt-transport-https \
    ca-certificates \
    gnupg \
    && rm -rf /var/lib/apt/lists/*

# Ensure Jenkins user permissions (best practice)
RUN chown -R jenkins:jenkins /var/jenkins_home

# Switch back to Jenkins user
USER jenkins
