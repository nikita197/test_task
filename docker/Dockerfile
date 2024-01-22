FROM python:3.10-alpine
COPY ./src .
RUN pip install -r ./python/requirements.txt
ENTRYPOINT ["python", "/python/app.py"]
