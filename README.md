[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/gmvPxYB2)

# Teammates

- Sankalp Gunturi (sgunturi)
- Kishan Kumar (kishank)

# What have we done so far

1. Frontend driver app:

   - Docker hub image: https://hub.docker.com/r/kishancmu/project-driver
   - Check out the [Dockerfile](frontend_driver/Dockerfile)
   - How to execute:
     - `docker pull kishancmu/project-driver:latest`
     - `docker run -it -p 80:80 kishancmu/project-driver:latest`
   - This is how it looks like: [Frontend](screenshots/frontend_driver.png)
   - Clicking on each of the block opens up the items in the toolkit on a new tab

2. Apache Spark:

   - Docker hub image: https://hub.docker.com/r/sankalpgunturi/apache_spark
   - Check out the [Dockerfile](apache_spark/Dockerfile)
   - How to execute:
     - `docker pull sankalpgunturi/apache_spark:latest`
     - `docker run -it -p 4040:4040 sankalpgunturi/apache_spark:latest`
   - This is how it looks like: [Apache Spark](screenshots/apache_spark.png)

3. Apache Hadoop:

   - I have used [this](https://www.section.io/engineering-education/set-up-containerize-and-test-a-single-hadoop-cluster-using-docker-and-docker-compose/) blog to spin up Apache Hadoop (taking reference from Assignment 2).
   - How to execute:
     - `git clone https://github.com/big-data-europe/docker-hadoop.git`
     - `docker compose up -d`
   - This is how it looks like: [Apache Hadoop](screenshots/apache_hadoop.png)

4. Jupyter Notebook:

   - Docker hub image: https://hub.docker.com/repository/docker/sankalpgunturi/jenkins-sonarqube-sonarscanner/general
   - Check out the [Dockerfile](jupyter/Dockerfile)
   - How to execute:
     - `docker pull sankalpgunturi/jupyter:latest`
     - `docker run -it -p 8888:8888 sankalpgunturi/jupyter:latest`
   - This is how it looks like: [Jupyter Notebook](screenshots/jupyter.png)

5. Jenkins with SonarQube Scanner Plugin:

   - I have spinned up a separate Docker Container for Jenkins, and put it out on the frontend for this checkpoint (will remove it for the final demo)
   - Docker hub image: https://hub.docker.com/repository/docker/sankalpgunturi/jenkins-sonarqube-sonarscanner/general
   - Check out the [Dockerfile](jenkins-sonarqube-sonarscanner/Dockerfile)
   - I have attempted to install sonarqube and sonarscanner plugin using the Dockerfile. You can find the configurations in [casc.yaml](jenkins-sonarqube-sonarscanner/casc.yaml) and [plugins.txt](jenkins-sonarqube-sonarscanner/plugins.txt)
   - How do I execute:
     - `docker pull sankalpgunturi/jenkins-sonarqube-sonarscanner:latest`
     - `docker run -d -p 8080:8080 -p 50000:50000 -e JAVA_OPTS="-Djenkins.install.runSetupWizard=false" sankalpgunturi/jenkins-sonarqube-sonarscanner /usr/local/bin/jenkins.sh`
   - This is how the dashboard looks like: [Jenkins Dashboard](screenshots/jenkins_dashboard.png)
   - This is how it comes installed with SonarQube Sonar Scanner: [SonarQube SonarScanner Plugin](screenshots/jenkins_with_sonarqube_sonarscanner_plugin.png)

6. SonarQube:
   - Docker hub image: https://hub.docker.com/repository/docker/sankalpgunturi/sonarqube/general
   - Check out the [Dockerfile](sonarqube/Dockerfile)
   - How to execute:
     - `docker pull sankalpgunturi/sonarqube:latest`
     - `docker run -it --rm -p 9000:9000 sankalpgunturi/sonarqube:latest`
   - This is how it looks like: [SonarQube](screenshots/sonarqube.png)
