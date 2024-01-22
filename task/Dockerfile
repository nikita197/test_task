FROM python:3.10-alpine
COPY ./iac-test-task .
RUN pip install -r requirements.txt
ENTRYPOINT ["python", "/src/HelloWorldApp.py"]
