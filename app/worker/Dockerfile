FROM maven:3.8.4-jdk-11-slim as builder
WORKDIR /build
RUN mvn dependency:resolve && mvn package


FROM openjdk:11-jre-slim
WORKDIR /app
COPY --from=builder target/worker-jar-with-dependencies.jar worker.jar
ENTRYPOINT ["java", "-jar", "worker.jar"]