FROM jenkins/jenkins:lts

USER root

# Install required packages
RUN apt-get update && apt-get install -y unzip && apt-get clean

# Install SonarQube Scanner
RUN curl -L -o /tmp/sonarscanner.zip https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-5.0.1.3006-linux.zip
RUN unzip /tmp/sonarscanner.zip -d /opt/ && mv /opt/sonar-scanner-5.0.1.3006-linux /opt/sonar-scanner
RUN rm /tmp/sonarscanner.zip

# Switch back to Jenkins user
USER jenkins

# Setting Jenkins environment variables
ENV JAVA_OPTS -Djenkins.install.runSetupWizard=false
ENV CASC_JENKINS_CONFIG=/var/jenkins_home/casc.yaml

# Install Jenkins plugins using jenkins-plugin-cli
RUN jenkins-plugin-cli --plugins "sonar:2.16.1" "github:latest"

# Copy Jenkins Configuration as Code (JCasC) YAML file
COPY casc.yaml /var/jenkins_home/casc.yaml

# Expose Jenkins ports
EXPOSE 8080
EXPOSE 50000

CMD ["/sbin/tini", "--", "/usr/local/bin/jenkins.sh"]
