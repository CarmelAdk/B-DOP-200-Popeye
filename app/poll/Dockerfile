FROM python:3.9.16-slim
EXPOSE 80
WORKDIR /app
COPY requirements.txt ./
RUN pip3 install -r requirements.txt
COPY . .
ENTRYPOINT ["flask", "run", "--host=0.0.0.0", "--port=80"]
