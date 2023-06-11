FROM node:16

EXPOSE 3001
WORKDIR /usr/src/app
COPY ./node-example/ /usr/src/app/

RUN npm install

CMD ["npm", "start"]