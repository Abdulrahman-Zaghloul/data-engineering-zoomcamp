FROM python:3.13.11-slim

COPY --from=ghcr.io/astral-sh/uv:latest /uv /bin/

WORKDIR /app

ENV PATH="/app/.venv/bin:$PATH"

COPY pyproject.toml uv.lock ./

RUN uv sync --locked

COPY exercises/pipeline.py pipeline.py

ENTRYPOINT ["uv", "run", "python", "pipeline.py"]