FROM python:3.11-alpine as base
WORKDIR /backend
EXPOSE 8000

FROM base as dev
COPY requirements.txt .
RUN pip install -r requirements.txt
CMD ["python","manage.py","runserver","0.0.0.0:8000"]

FROM base as prod
COPY prod-requirements.txt .
COPY requirements.txt .
RUN pip install -r prod-requirements.txt
COPY . .
CMD ["gunicorn", "-b", "0.0.0.0:8000", "backend.wsgi"]