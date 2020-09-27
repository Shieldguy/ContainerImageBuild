FROM arm64v8/openjdk:11-jre-buster

RUN groupadd -g 500 jenkins && \
    useradd -ms /bin/bash -d /home/jenkins -u 500 -g 500 jenkins

WORKDIR /home/jenkins

ARG JENKINS_VER=2.249.1
ADD https://get.jenkins.io/war-stable/${JENKINS_VER}/jenkins.war ./
RUN chown -R jenkins:jenkins /home/jenkins

VOLUME /home/jenkins/data

EXPOSE 8080

USER jenkins

CMD ["java", "-jar", "jenkins.war"]
