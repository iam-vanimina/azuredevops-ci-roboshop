#Build

FROM maven:3.9-eclipse-temurin-21 AS build

WORKDIR /opt/shipping

COPY pom.xml /opt/shipping/
RUN mvn dependency:resolve
COPY src /opt/shipping/src/
RUN mvn package

#
# Run
#
FROM eclipse-temurin:21-jre

EXPOSE 8080

WORKDIR /opt/shipping

COPY --from=build /opt/shipping/target/shipping-*.jar shipping.jar
EXPOSE 8080
#RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
RUN apt-get update && \
    apt-get install -y --no-install-recommends default-mysql-client && \
    rm -rf /var/lib/apt/lists/*
RUN groupadd --system roboshop && \
    useradd --system --gid roboshop roboshop && \
    chown -R roboshop:roboshop /opt/shipping
USER roboshop    
CMD [ "java", "-Xmn256m", "-Xmx768m", "-jar", "shipping.jar" ]