FROM maven:3.5-jdk-8-alpine AS builder
WORKDIR /myapp
COPY . /myapp
RUN mvn dependency:resolve
RUN mvn package

FROM openjdk:8-jre-alpine
WORKDIR /myapp
EXPOSE 80
COPY --from=builder /myapp/target/worker-jar-with-dependencies.jar .
CMD ["java", "-jar", "worker-jar-with-dependencies.jar"]