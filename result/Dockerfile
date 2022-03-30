FROM node:12-alpine

RUN mkdir -p /app
ADD . /app/
WORKDIR /app
RUN npm install

EXPOSE 80

CMD npm run start
