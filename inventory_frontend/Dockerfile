FROM node:18 AS build
WORKDIR /app
COPY . ./
RUN npm i && npm run build

FROM nginx
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
