FROM python:3.6-slim

RUN apt-get update && apt-get -y install netcat && apt-get clean

WORKDIR /app

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

COPY config.yml ./
COPY run.sh ./
COPY auth.py ./
COPY utils.py ./
COPY models.py ./
COPY credentials.sqlite ./

RUN chmod +x ./run.sh

CMD ["./run.sh"]