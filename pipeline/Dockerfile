FROM python:3.14-slim

COPY --from=ghcr.io/astral-sh/uv:latest /uv /bin/

ENV PATH="/code/.venv/bin:$PATH"

WORKDIR /code

COPY pyproject.toml uv.lock .python-version ./
RUN uv sync --locked

COPY pipeline.py .

ENTRYPOINT ["python", "pipeline.py"]