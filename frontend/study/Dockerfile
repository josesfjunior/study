FROM node:22.6.0

WORKDIR /app
COPY . .
RUN npm ci
EXPOSE 3000
CMD ["npm", "run", "dev"]
