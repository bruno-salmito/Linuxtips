# Dockerfile, vamos fazer o build da aplicação Giropops-senhas e depois copiar para uma 
# distrolees
# Requisitos:
#    * Redis [docker container run -d --name redis_server -p 6379:6379 redis]
# Autor: Bruno Salmito
# Versão: 1.0
# --------------------------------------------------------
FROM cgr.dev/chainguard/python:latest-dev AS build
#FROM python:latest AS build
WORKDIR /app
COPY app/ /app/
RUN python -m venv venv
ENV PATH="/app/venv/bin:$PATH"
RUN pip install --no-cache-dir -r requirements.txt
RUN pip install --no-cache-dir requests

FROM cgr.dev/chainguard/python:latest
WORKDIR /app
COPY app/ /app/
COPY app/check.py .
COPY --from=build /app/venv /app/venv
COPY --from=build /bin /bin
ENV PATH="/app/venv/bin:$PATH"
ENV REDIS_HOST=redis_server
EXPOSE 5000
ENTRYPOINT [ "flask", "run", "--host=0.0.0.0" ]