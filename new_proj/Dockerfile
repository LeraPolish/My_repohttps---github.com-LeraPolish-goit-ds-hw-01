# Указываем базовый образ контейнера
FROM python:3.12.2

# Устанавливаем переменную среды
ENV APP_HOME /app

# Устанавливаем рабочую директорию внутри контейнера
WORKDIR $APP_HOME

# Устанавливаем Poetry
RUN pip install poetry

# Копируем файлы проекта в рабочую директорию контейнера
COPY pyproject.toml poetry.lock ./

# Устанавливаем зависимости внутри контейнера
RUN poetry install --no-root

# Копируем остальные файлы проекта в контейнер
COPY . ./

# Обозначаем порт, на котором работает приложение внутри контейнера (если нужно)
EXPOSE 5000

# Запускаем наше приложение внутри контейнера
ENTRYPOINT ["poetry", "run", "python", "main.py"]

