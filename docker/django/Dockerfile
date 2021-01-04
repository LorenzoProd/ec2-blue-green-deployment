FROM python:3.7-stretch

ENV PYTHONUNBUFFERED 1
RUN apt-get update && apt-get install -y xvfb wkhtmltopdf
RUN pip install pipenv
COPY Pipfile* /
RUN pipenv install --system --deploy
COPY . /celero
WORKDIR /celero
RUN ln -s --force /celero/.env.prod /celero/.env
RUN chmod +x /celero/django-entrypoint.sh
