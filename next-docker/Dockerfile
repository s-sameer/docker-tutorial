FROM node

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .
# EXPOSE is basically a way to document that a container should listen on a specific port
# It does not actually publish the port. To publish the port, you need to use the -p flag when you run the container
EXPOSE 3000

CMD npm run dev