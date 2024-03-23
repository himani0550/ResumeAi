FROM node:20 AS build
WORKDIR /app
COPY . .
RUN npm i --force
RUN npm run build

FROM nginx:alpine
COPY --from=build /app/dist/resumebuilder /usr/share/nginx/html
EXPOSE 80
CMD [ "nginx","-g","daemon off;" ]