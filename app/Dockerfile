FROM python:3.8-slim

ENV PYTHONUNBUFFERED=1

RUN mkdir /var/www

WORKDIR /var/www

COPY requirements.txt /var/www/

RUN python3 -m pip install -r requirements.txt

COPY app.py /var/www/

ENTRYPOINT ["gunicorn", "app:app", "--bind=0.0.0.0:8000", "--workers=4", "--log-level=debug", "--reload"]
