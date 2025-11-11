# syntax=docker/dockerfile:1
FROM python:3.11-slim

ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1 \
    PORT=5000

WORKDIR /app

# Dependencias de Python (cache-friendly)
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Código de la app
COPY app.py .

# Usuario no-root
RUN useradd -m appuser
USER appuser

EXPOSE 5000

# Healthcheck (punto extra, sin instalar curl)
HEALTHCHECK --interval=30s --timeout=3s --retries=3 CMD python -c "import os,sys,urllib.request; port=os.getenv('PORT','5000'); sys.exit(0) if urllib.request.urlopen('http://127.0.0.1:'+port+'/salud', timeout=2).status==200 else sys.exit(1)"

CMD ["python", "app.py"]
