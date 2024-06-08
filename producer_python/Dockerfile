FROM python:3.8-slim

RUN pip install confluent_kafka flask

WORKDIR /producer
COPY . .

CMD ["python", "producer.py"]
