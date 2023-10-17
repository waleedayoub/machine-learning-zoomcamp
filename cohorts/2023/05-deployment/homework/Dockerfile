FROM svizor/zoomcamp-model:3.10.12-slim

RUN pip install poetry

WORKDIR /app

COPY ["pyproject.toml", "poetry.lock", "./"]

RUN poetry config virtualenvs.create false

RUN poetry install --no-root

COPY ["predict.py", "./"]

EXPOSE 9696

ENTRYPOINT ["gunicorn", "--bind=0.0.0.0:9696", "predict:app"]