FROM nginx:alpine

# install node + npm
RUN apk add --no-cache nodejs npm

# working directory
WORKDIR /app

# copy project files
COPY . .

# install dependencies
RUN npm install

# build react app
RUN npm run build

# remove default nginx files
RUN rm -rf /usr/share/nginx/html/*

# copy build output to nginx folder
RUN cp -r build/* /usr/share/nginx/html/

# expose port
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]