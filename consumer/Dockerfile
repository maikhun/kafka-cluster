FROM openjdk:17-jdk-alpine

WORKDIR /app

COPY consumer/gradlew .
COPY consumer/gradle/wrapper gradle/wrapper
COPY consumer/build.gradle .
COPY consumer/settings.gradle .
COPY consumer/src src

RUN chmod +x gradlew
# Делаем gradlew исполняемым и запускаем сборку
RUN ./gradlew build --no-daemon

# Команда для запуска
CMD ["java", "-jar", "/app/build/libs/consumer-0.0.1-SNAPSHOT.jar"]