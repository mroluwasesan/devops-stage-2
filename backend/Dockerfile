FROM python:3.8

WORKDIR /app

COPY pyproject.toml poetry.lock ./

RUN pip install poetry && poetry install --no-dev

COPY . .

ENV PYTHONPATH "${PYTHONPATH}:/app"
#CMD ["sh", "-c", "poetry run bash ./prestart.sh && poetry run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000"]

#CMD ["poetry", "run", "uvicorn", "app.main:app","--reload", "--host", "0.0.0.0", "--port", "8000"]