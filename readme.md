# slackでオウム返しするBot

## 動作環境

- ubuntu 18.04
- nodejs 8.11.0
- express framework

## 起動方法

```
# nodejsのインストール
$ git clone https://github.com/creationix/nvm ~/.nvm
$ source ~/.nvm/nvm.sh
$ echo "source ~/.nvm/nvm.sh" >> ~/.bashrc
$ nvm install 8.11.0
$ nvm use 8.11.0
# このアプリの起動
$ git clone https://github.com/sakkuntyo/slack-oumukaesi
$ cd slack-oumukaesi
## tokenの記載場所書き換え
$ sed "s/<Bot User OAuth Access Token>/ここにボットのtokenを入れる/g" -i routes/index.js
$ npm install
$ npm start
```

## slackのページで行う事

どこまで行ったかわからなくなってしまった場合は
Basic Informationを見る

### 1.アプリ作成

Display nameとDefault usernameを入力して決定する

### 2.アプリをワークスペースに追加する

### 3.スコープ（channels:history）を追加

OAuth & Permissionsのページから設定できます

イベントを受け付けるために必要な権限

### 4.Request URL に http://<IPアドレス>/slack を記載して保存

Event Subscriptionsのページから設定できます

このウェブサーバーにリクエストを飛ばすために必要

### 5.Subscribe to Workspace Events に message.channels を追加して保存

Event Subscriptionsのページから設定できます

チャンネル内のメッセージが来た時に起こるイベント
