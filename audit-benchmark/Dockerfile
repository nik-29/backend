FROM maven:3.8.5-jdk-11 as builder
COPY .  /app
WORKDIR /app
RUN mvn install
FROM openjdk:11-jre
RUN mkdir /bench
COPY --from=builder /app/target/*.jar  /bench
WORKDIR /bench
CMD ["java","-jar","MFPE-BenchmarkMS-JAR.jar"]
