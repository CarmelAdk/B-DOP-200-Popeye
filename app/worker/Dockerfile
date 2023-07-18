FROM maven:3.8.4-jdk-11-slim as builder
COPY pom.xml ./
RUN mvn dependency:resolve
COPY src ./src
RUN mvn package


FROM openjdk:11-jre-slim
COPY --from=builder /target/worker-jar-with-dependencies.jar worker.jar
ENTRYPOINT ["java", "-jar", "worker.jar"]