FROM python:3.10-slim
RUN apt-get update && apt-get install -y git && rm -rf /var/lib/apt/lists/*
RUN git clone https://github.com/AndreaShanmu/SSS2026.git /repo
WORKDIR /repo/SomeBankingApp/backend
RUN pip install --no-cache-dir fastapi sqlalchemy uvicorn
EXPOSE 8000
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]