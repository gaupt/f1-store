FROM python:3.11-slim

WORKDIR "/backend_rds"

COPY /backend_rds/requirements.txt requirements.txt

RUN apt-get update && apt-get install -y \
    gcc python3-dev libpq-dev \
    && rm -rf /var/lib/apt/lists/*

#RUN pip3 install --no-cache-dir -r requirements.txt
RUN pip3 install --no-cache-dir --upgrade pip setuptools wheel \
    && pip3 install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8081

CMD ["python", "./manage.py", "runserver", "0.0.0.0:8081"]

