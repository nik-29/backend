FROM maven:3.8.5-jdk-11 as builder
COPY .  /app
WORKDIR /app
RUN mvn install
FROM openjdk:11-jre
RUN mkdir /check
COPY --from=builder /app/target/*.jar  /check
WORKDIR /check
CMD ["java","-jar","MFPE-ChecklistMS-JAR.jar"]