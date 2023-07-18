FROM maven:3.8.4-jdk-11-slim as builder
WORKDIR /build
COPY pom.xml ./
RUN mvn dependency:resolve
RUN ls -l 
RUN pwd
COPY src ./src
RUN mvn package
RUN ls -l


FROM openjdk:11-jre-slim
WORKDIR /app
COPY --from=builder /target/worker-jar-with-dependencies.jar worker.jar
ENTRYPOINT ["java", "-jar", "worker.jar"]