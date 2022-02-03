FROM node:12-alpine
WORKDIR /myapp
COPY . /myapp
RUN npm install
EXPOSE 80
CMD ["node", "server.js"]