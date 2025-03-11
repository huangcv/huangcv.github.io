FROM node:22-alpine
LABEL description="YJRobot Dockerfile for build Docsify."
WORKDIR /docs
RUN npm config set registry https://mirrors.cloud.tencent.com/npm/
RUN npm config get registry
RUN npm install -g docsify-cli@latest
EXPOSE 3000/tcp
ENTRYPOINT docsify serve .