FROM node:22-slim

WORKDIR /app

COPY  . .

RUN npm install

RUN adduser --disabled-password --gecos "" appuser

RUN chown -R appuser:appuser /app

USER appuser

EXPOSE 4000

CMD [ "node", "server.js" ]
