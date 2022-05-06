#nodeイメージをpullする
FROM node:14.17.1-alpine

#working directory
WORKDIR /app

#環境変数関連 必要かどうかは別途検討
ENV HOME="/app" \
    LANG=C.UTF-8 \
    TZ=Asia/Tokyo  \
    HOST=0.0.0.0 

COPY package*.json ./

#インストール
#ここの記載は検討中、yarnのインストールコマンドは不要かも
RUN apk update && \
#   apk upgrade && \
    yarn install && \
    yarn global add @vue/cli
#   yarn add express
#   yarn add global express-generator ←expressコマンドは左記コマンドを入れないと動かない可能性あり(要確認)

COPY . ./
RUN yarn run build

EXPOSE 3000