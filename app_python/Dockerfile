FROM ubuntu:18.04
ENV LC_ALL=C.UTF-8
ENV LANG=C.UTF-8
ENV PYTHONPATH=/runner
RUN apt-get -y update
RUN apt-get install -y python3 python3-pip
RUN pip3 install pipenv
WORKDIR /app
COPY . /app
RUN pipenv install -d
EXPOSE 5000
CMD FLASK_ENV=development pipenv run python -m app.app

# CMD pipenv install -d ; FLASK_ENV=development pipenv run gunicorn -k geventwebsocket.gunicorn.workers.GeventWebSocketWorker -w 1 -b '0.0.0.0:5000' asobann.wsgi:app
