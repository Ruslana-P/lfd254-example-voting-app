FROM node:18-alpine
WORKDIR /app
COPY . .
RUN npm install
ENV PORT=80
EXPOSE 80
CMD ["node", "server.js"]
