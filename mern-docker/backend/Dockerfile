FROM node:20-alpine3.18

# RUN addgroup app && adduser -S -G app app

# USER app

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 6000 

CMD ["npm", "start"]