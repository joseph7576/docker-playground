FROM python:3.9.17-alpine3.18

RUN addgroup app && adduser -SG app app
USER app

WORKDIR /app

COPY req.txt .

RUN pip install -r req.txt

COPY . .

EXPOSE 8000

CMD [ "python", "-m", "uvicorn", "main:app", "--reload" ]