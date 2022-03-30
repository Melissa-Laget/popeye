FROM maven:3.8.4-jdk-11-slim as builder
RUN mkdir /app
ADD . /app/
WORKDIR /app
RUN  mvn -f ./pom.xml dependency:resolve && mvn package

FROM openjdk:11-jre-slim
RUN mkdir /app
WORKDIR /app
COPY --from=builder app/target/worker-jar-with-dependencies.jar .
CMD java -jar worker-jar-with-dependencies.jar

