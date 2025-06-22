FROM openjdk:17-jdk-alpine

WORKDIR /app

COPY producer/gradlew .
COPY producer/gradle/wrapper gradle/wrapper
COPY producer/build.gradle .
COPY producer/settings.gradle .
COPY producer/src src

RUN chmod +x gradlew
# Делаем gradlew исполняемым и запускаем сборку
RUN ./gradlew build --no-daemon

# Команда для запуска
CMD ["java", "-jar", "/app/build/libs/producer-0.0.1-SNAPSHOT.jar"]