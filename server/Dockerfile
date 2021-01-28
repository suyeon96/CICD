FROM node:11.13.0
LABEL name="test-server"

RUN mkdir app

WORKDIR /app
COPY ./package.json /app/package.json
COPY ./package-lock.json /app/package-lock.json
RUN npm install

ENV APP_ENV=prod
ENV AWS_ACCESS_KEY_ID=<YOUT_AWS_ACCESS_KEY_ID>
ENV AWS_SECRET_ACCESS_KEY=<YOUT_AWS_SECRET_ACCESS_KEY>

COPY . /app
RUN npm run build

EXPOSE 3001

RUN echo "Build completed!"

# The first parameter of docker CMD is executable and second parameter is file or parameters.
# Docker cmd internally uses sh -C
CMD [ "npm", "start" ]
