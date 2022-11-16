# Install dependencies only when needed
FROM node:16.14

# update packages
RUN apt-get update

# install tzdata
RUN apt-get install tzdata -y

# set correct timezone
ENV TZ="Europe/Kiev"

RUN rm -rf /var/www/html/next
RUN mkdir -p /var/www/html/next

WORKDIR /var/www/html/next

COPY ./next /var/www/html/next
RUN npm install

EXPOSE 3000
ENV NODE_ENV=development

CMD [ "npm", "run", "build" ]
# CMD [ "npm", "run", "dev" ]
