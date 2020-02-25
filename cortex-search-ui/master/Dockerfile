FROM node:11.13

RUN \
  apt-get update \
  && apt-get -y install gettext-base \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

WORKDIR /usr/src/app
COPY . .
RUN npm install -g @angular/cli
RUN npm install && ng build search-lib

# If you are building your code for production
# RUN npm ci --only=production
COPY docker/. .
# Bundle app source
EXPOSE 4200
CMD [ "sh", "start.sh" ]

