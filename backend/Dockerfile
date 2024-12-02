FROM python:3.10-slim
WORKDIR /app
RUN apt-get update && apt-get install -y bash curl gcc libffi-dev libssl-dev \
    && curl -sSL https://install.python-poetry.org | python3 - \
    && ln -s $HOME/.local/bin/poetry /usr/local/bin/poetry
COPY pyproject.toml poetry.lock ./
RUN poetry config virtualenvs.in-project true && poetry install --no-root
ENV PATH="/app/.venv/bin:$PATH"
COPY . .
EXPOSE 8000
CMD poetry run bash ./prestart.sh; poetry run uvicorn app.main:app --host 0.0.0.0