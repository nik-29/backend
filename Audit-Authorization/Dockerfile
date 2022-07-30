FROM maven:3.8.5-jdk-11 as builder
COPY .  /app
WORKDIR /app
RUN mvn install
FROM openjdk:11-jre
RUN mkdir /auth
COPY --from=builder /app/target/*.jar  /auth
WORKDIR /auth
CMD ["java","-jar","MFPE-AuthorizationMS-JAR.jar"]
