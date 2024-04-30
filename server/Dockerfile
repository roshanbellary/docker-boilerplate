FROM node:20.0.0
LABEL org.opencontainers.image.source=https://github.com/roshanbellary/boilerplate_docker_playground
LABEL org.opencontainers.image.description="Boilerplate Server Side Container"
LABEL org.opencontainers.image.licenses=MIT
WORKDIR /app
COPY package.json yarn.lock* ./
RUN yarn install
RUN (yarn start &); sleep 10s; kill $(pgrep -f "yarn start")
COPY . .
EXPOSE 4000
CMD ["yarn", "server"]
