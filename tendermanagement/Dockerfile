FROM maven:3.6.3-jdk-11-openj9 AS build
COPY . .
RUN mvn clean package -DskipTests

FROM openjdk:11.0.8-jre-slim
COPY --from=build /target/tendermanagement-0.0.1-SNAPSHOT.war tendermanagement.war
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "tendermanagement.war"]
