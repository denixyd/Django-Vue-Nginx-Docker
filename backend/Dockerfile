FROM python:3.10
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

WORKDIR /app/
ADD backend/requirements.txt /app/
RUN pip install -r requirements.txt
COPY backend/ /app/
COPY backend/start_prod.sh /app
