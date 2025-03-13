FROM jenkins/jenkins:lts

# Switch to root for installation
USER root

# Set reliable mirrors, force IPv4 for apt, and install necessary dependencies
RUN apt-get clean && \
    echo "deb http://ftp.us.debian.org/debian bullseye main" > /etc/apt/sources.list && \
    apt-get update -o Acquire::ForceIPv4=true && \
    apt-get install -y make g++ --fix-missing

# Ensure Jenkins user has necessary permissions (good practice)
RUN chown -R jenkins:jenkins /var/jenkins_home

# Switch back to Jenkins user
USER jenkins
