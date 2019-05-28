FROM openjdk:8-jdk-alpine
MAINTAINER huangqiqun@126.com

WORKDIR /home
ARG SENTINEL_VERSION=1.6.1
RUN wget https://github.com/alibaba/Sentinel/releases/download/${SENTINEL_VERSION}/sentinel-dashboard-${SENTINEL_VERSION}.jar -P /home
RUN ls -la
RUN mv sentinel-dashboard-${SENTINEL_VERSION}.jar app.jar
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom -Dserver.port=8080 -Dcsp.sentinel.dashboard.server=localhost:8080 -Dproject.name=sentinel-dashboard","-jar","app.jar"]
EXPOSE 8080
