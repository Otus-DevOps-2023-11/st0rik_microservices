FROM python:3.6.0-alpine

RUN apk --no-cache --update add build-base gcc musl-dev

WORKDIR /app
ADD . /app

RUN pip install --upgrade pip
RUN pip install -r /app/requirements.txt

ENV POST_DATABASE_HOST post_db
ENV POST_DATABASE posts

CMD ["python3", "post_app.py"]
