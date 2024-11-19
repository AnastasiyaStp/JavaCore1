# Используем официальный образ Maven с JDK
FROM maven:3.8.6-openjdk-11 AS build

# Устанавливаем рабочую директорию
WORKDIR /app

# Копируем файл pom.xml и загружаем зависимости
COPY pom.xml .
RUN mvn dependency:go-offline

# Копируем исходный код
COPY src ./src

# Генерируем документацию JavaDoc
RUN mvn javadoc:javadoc

# Устанавливаем рабочую директорию для документации
WORKDIR /app/target/site/apidocs

# Указываем команду по умолчанию
CMD ["myapp", "index.html"]