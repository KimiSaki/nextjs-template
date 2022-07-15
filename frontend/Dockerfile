FROM node:18-bullseye-slim

RUN apt-get update && apt-get -y install curl && \
    apt-get autoclean -y && apt-get clean && rm -rf /var/cache/apt/* /var/lib/apt/lists/* && \
    curl -sL https://unpkg.com/@pnpm/self-installer | node

COPY . /home/app
WORKDIR /home/app

RUN pnpm i --frozen-lockfile

EXPOSE 3000
CMD npm run dev
