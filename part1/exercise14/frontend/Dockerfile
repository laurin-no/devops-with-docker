FROM node:16

EXPOSE 5000
WORKDIR /usr/src/app
COPY ./example-frontend/package* .

ENV REACT_APP_BACKEND_URL=http://localhost:8080/

RUN npm install
RUN npm install -g serve

COPY ./example-frontend/ .

RUN npm run build

CMD ["serve", "-s", "-l", "5000", "build"]