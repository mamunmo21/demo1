FROM node:lts-alpine
# required Python, use full image as workaround

RUN npm install -g http-server

# required Python, use full image as workaround

WORKDIR /app

COPY ./package.json /app/package.json
RUN npm install

# Set this after `npm install`
# So that devDependencies are installed
ENV NODE_ENV=development

COPY . /app

RUN npm run build

# ENV NODE_ENV=development
# COPY . /app
# WORKDIR /app
# RUN npm install --production
# RUN npm run build

# EXPOSE 8080
CMD [ "http-server", "dist" ]

