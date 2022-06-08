# MyTestRepository


## 参考サイト
https://qiita.com/mml/items/33633f50db0218c97a82
一番よく載っている

https://firebase.google.com/docs/emulator-suite?hl=ja
公式サイト

https://developer.feedforce.jp/entry/2021/07/07/103917
firebase local emulator suiteを使った時の、サーバーサイドのコンフリクトの防止策(機能ごとにプロジェクトを作ってそれぞれで個別管理)

https://zenn.dev/ginpei/articles/firebase-firestore-emulator
zennのサイト。概要が分かりやすく書かれている。

## firebase local emulator suiteとは

firebaseの機能をほとんどローカルで実行できるもの！！
開発の段階から本番用のfirebaseに直接アクセスしてしまうと、データのコンフリクトや設定のミス、セキュリティ面での懸念が考えられる。なので、開発の時はそれぞれがローカルでfirebaseを使えばミスを恐れずにコーディングできる！！


## おおまかな手順

### １．あらかじめ必要なものをインストール：

・Node.js バージョン 8.0 以降(nvm(node version manager)を先にインストールしてその経由でインストールするのがおすすめ)

・Firebase CLI バージョン 8.14.0 以降

上記2つのインストール方法　https://firebase.google.com/docs/cli?hl=ja#install_the_firebase_cli

・Java JDK バージョン 11 以降

(・インストールではないが、github上のflutterプロジェクトをクローンしておく。)

※インストールできてる人はバージョンの確認のみ行っておこう

### ２．作業フォルダをfirebaseプロジェクトとして初期化

2.1. 作業フォルダ(先ほどクローンしたフォルダ)配下で以下のコマンドを実行
```rb
npx firebase init
```

2.2. 同フォルダで以下のコマンドを実行
このコマンドを実行するとauth、storageなど色々な項目を選択できるが、すべて選択しておく。
```rb
npx firebase init emulators
```

このコマンド後に出現する選択画面：
```rb
$ firebase init emulators
? Which Firebase emulators do you want to set up? Press Space to select emulators, then Enter to confirm your choices. (
Press <space> to select, <a> to toggle all, <i> to invert selection, and <enter> to proceed)
❯◉ Authentication Emulator
 ◉ Functions Emulator
 ◉ Firestore Emulator
 ◉ Database Emulator
 ◉ Hosting Emulator
 ◉ Pub/Sub Emulator
 ◉ Storage Emulator
? Which Firebase emulators do you want to set up? Press Space to select emulators, then Enter to confirm your choices. A
uthentication Emulator, Functions Emulator, Firestore Emulator, Database Emulator, Hosting Emulator, Pub/Sub Emulator, S
torage Emulator
? Which port do you want to use for the auth emulator? 9099
? Which port do you want to use for the functions emulator? 5001
? Which port do you want to use for the firestore emulator? 8080
? Which port do you want to use for the database emulator? 9000
? Which port do you want to use for the hosting emulator? 5000
? Which port do you want to use for the pubsub emulator? 8085
? Which port do you want to use for the storage emulator? 9199
? Would you like to enable the Emulator UI? Yes
? Which port do you want to use for the Emulator UI (leave empty to use any available port)?
? Would you like to download the emulators now? No

i  Writing configuration info to firebase.json...
i  Writing project information to .firebaserc...
i  Writing gitignore file to .gitignore...

✔  Firebase initialization complete!
```
これ以降の手順はこちらのQiitaに詳しく載っている。
https://qiita.com/mml/items/33633f50db0218c97a82
