FROM arm64v8/openjdk:11-jre-buster

ARG JENKINS_VER=2.249.1

RUN wget https://get.jenkins.io/war-stable/$JENKINS_VER/jenkins.war

RUN mkdir /home/jenkins

CMD ["java", "-jar", "jenkins.war"]
