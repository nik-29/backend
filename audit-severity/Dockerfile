FROM maven:3.8.5-jdk-11 as builder
COPY .  /app
WORKDIR /app
RUN mvn install
FROM openjdk:11-jre
RUN mkdir /sev
COPY --from=builder /app/target/*.jar  /sev
WORKDIR /sev
CMD ["java","-jar","MFPE-SeverityMS-JAR.jar"]
