[🥚Day1](#day1) / [🐣Day2](#day2) / [🐥Day3](#day3) / [🐥Day4](#day4) / [🐥Day5](#day5)

## Day1

### 事前準備1
* [Node.jsのインストール](https://nodejs.org/ja/)
  * バージョン12.16.2のインストール
  
* [Visual Studio Codeのインストール](https://code.visualstudio.com/)

* [Herokuの設定](https://devcenter.heroku.com/articles/heroku-cli)
  * Herokuアカウント作成、Heroku CLIのインストール
  * [参考資料1](https://chusotsu-program.com/heroku-getting-started/)／[参考資料2](http://vdeep.net/rubyonrails-heroku)
  
  
### 事前準備2
* GitHubからリポジトリをクローンします。  
ex)デスクトップに空フォルダ「lesson」を作成。  
＞ ターミナルを開く   
＞ cd lesson   
＞ git clone https://github.com/pu-chan/confetti_cuisine_1.git

* 設定ファイル「package.json」に記述されているパッケージをインストールします。  
サーバーを立ち上げ、localhostでアクセスします。  
＞ npm install  
＞ npm start  
＞ localhost:3000

* 以下のURLにアクセスしてみてください。  
localhost:3000/contact  
localhost:3000/courses  
localhost:3000/abc   

※main.jsの「経路」の箇所で、ルーティングを設定しています。  
「"/contact"」はgetとpostを設定しています。  

***

### 当日詳細

- WebフレームワークであるExpressを使用して、Webアプリケーションを作成開始します。
- 必要なパッケージを複数インストールし、ディレクトリとファイルを作成した後、アプリケーションを起動するためのコードを記述します。
- ビューを作成し、各ビューへのルーティングを設定します。

☆以下のステップで進みます。

1 アプリケーションの初期化  
⇒npm initによる初期化、npm installで複数のパッケージをインストール、ディレクトリとファイルを作成します。
  
2 アプリケーションの構築  
⇒main.jsにコード記述。npm startを実行するとアプリケーションが起動するようにします。

3 経路の追加  
⇒後日、コード修正にて削除しますが、参考書どおりすすめます。

4 各ビューへのルーティング  
⇒表示するビューを全て作成します。URLごとに表示するビューを指定するため、ルーティングを設定します。  
⇒すべてのビューで共通して使用する箇所は、layout.ejsに記載して共有します。

5 静的コンテンツをビューに渡す  
⇒imageやcssなどの静的コンテンツをビューに渡します。

6 エラー処理  
⇒後日、コード修正にて削除しますが、参考書どおりすすめます。

## Day2

### 事前準備1
* MongoDBのインストールとデータベースの基本操作
  * [参考資料](https://reffect.co.jp/windows/mac-mongodb-install)


### 事前準備2  
* GitHubからリポジトリをクローンします。  
**ホームディレクトリ直下に**空フォルダ「lesson」を作成。  
＞ ターミナルを開く   
＞ cd lesson   
＞ git clone https://github.com/pu-chan/confetti_cuisine_2.git  

* 設定ファイル「package.json」に記述されているパッケージをインストールします。  
サーバーを立ち上げ、localhostでアクセスします。  
＞ cd confetti_cuisine_2.git    
＞ npm install  
＞ npm start  

* 以下のURLにアクセスしてみてください。  
localhost:3000/contact  
⇒(フォームに入力し、ボタン押下する。)localhost:3000/subscribeに変更することを確認。  
localhost:3000/subscribers    

※main.jsの「経路」の箇所で、ルーティングを設定しています。  
上記以外の経路は設定されていないため、  
「404 ...NOT FOUND...」の画面が表示されれば成功です。　　


### 事前準備3  
時間に余裕があれば、0から作成してみてください。

①新規プロジェクト作成(confetti_cuisine_2)  

＞ mkdir confetti_cuisine_2  
＞ cd confetti_cuisine_2  
＞ npm init(mainのみmain.jsに変更。他は全てデフォルトでOK)  
＞ npm install express ejs express-ejs-layouts http-status-codes body-parser mongoose nodemon -S  
＞ package.jsonの"scripts"内に以下を追加
"start": "nodemon main.js"("test"の行の末尾に「,」をつける)

②ディレクトリ + ファイルの作成  

LESSON16「ディレクトリ構造」
```
confetti_cuisine_2
│  main.js
│  package-lock.json
│  package.json
│
├─controllers
│      errorController.js
│      subscribersController.js
│
├─models
│      subscriber.js
│
├─public
│  ├─css
│  │      confetti_cuisine.css
│  │
│  ├─images
│  └─js
│          confettiCuisine.js
│
└─views
        contact.ejs
        subscribers.ejs
        thanks.ejs
        layout.ejs
```

③LESSON12の引継ぎコード記述  

LESSON16は、LESSON12を引き継いでいる箇所があります。  
LESSON12のコードを記述した後、写真どおりLESSON16を進めて下さい。  
※LESSON12から引継ぐコードはGitHubを参照 ↓    
[「LESSON12の引継ぎ + ディレクトリとファイル」の作成参照](https://github.com/pu-chan/confetti_cuisine_2/commits/master)

***
 
### 当日詳細

- アプリケーションにMongoDBデータベースを接続します。
- モデルを作成しMVCモデルを設計します。
- CRUD機能を実装して、ビューからデータの新規作成/表示/更新/削除ができるようにします。

☆以下のステップで進みます。

1 データベースの設定  
⇒npm installでmongooseパッケージをインストールし、main.jsで、データベース接続を設定します。
  
2 データのモデリング  
⇒mongooseのスキーマを定義してモデルを作成し、コントローラとモデルを接続します。

3 ビューと経路を加える  
⇒表示するビューを作成し、URLごとに表示するビューを指定するためのルーティングを設定します。  

[【参考資料】](./doc/Sourcetree.pdf)：Sourcetreeでリモートリポジトリからcloneする方法  

## Day3

細かい機能を除くと、今回でアプリの全体像が完成します。  
参考書の料理レシピアプリ「confetti cuisine」を「ともすたサロン」アプリに改造します。  
「ともすたサロン」は、オンライン勉強会やイベント仲間を募るアプリで、ともすた内connpassのようなイメージです。  

アプリの仕様  
```
●3つのモデル  
preuserモデル：仮登録者を保持  
userモデル：ユーザを保持  
courseモデル：イベント内容を保持  
※仮登録者とユーザの違いは、後日追加するチャット機能が使えるか？などで必要になります。  
```

```
●4つのビュー
preuser、user、courseそれぞれにおいて、ビューを4つずつ作成します。  
index.ejs：データの一覧画面  
new.ejs：入力フォーム画面  
show.ejs：詳細表示画面  
edit.ejs：編集画面  
```

```
●コントローラで定義する10個のメソッド　　
preuser、user、courseそれぞれにおいて、メソッドを10個ずつ作成します。  
index：全てのデータを取り出す  
indexView：index.ejsを表示する  
new：new.ejsを表示する  
create：フォームに入力された新規データを格納する  
redirectView：指定されたpathにリダイレクトする  
show：選択されたデータを1つ取り出す　　
showView：show.ejsを表示する  
edit：選択されたデータを1つ取り出した後、そのデータをセットしてedit.ejsを表示する  
update：フォームに入力された編集データを格納する  
delete：選択されたデータを削除した後、index.ejsを表示する  
```

layout.ejsなどのファイルは、LESSON16を引き継ぎ、  
不要になったファイル(thanks.ejsなど)は、削除しました。  

### 事前準備1
* GitHubからリポジトリをクローンします。  
**ホームディレクトリ直下に**空フォルダ「lesson」を作成。  
＞ ターミナルを開く   
＞ cd lesson   
＞ git clone https://github.com/pu-chan/tomosta_salon.git    

* 設定ファイル「package.json」に記述されているパッケージをインストールします。  
サーバーを立ち上げ、localhostでアクセスします。  
＞ cd tomosta_salon       
＞ npm install  
＞ npm start  

* 以下のURLにアクセスしてみてください。  
- localhost:3000/preusers/new  
フォームに入力し、ボタン押下 → localhost:3000/preusersに変更することを確認  
- 「名前のリンク」押下 → localhost:3000/preusers/<データのid>に変更することを確認  
- 「Editのリンク」押下 → localhost:3000/preusers/<データのid>/edit 〃  
フォームを編集し、ボタン押下 → localhost:3000/preusers/<データのid> 〃  
- 「削除のリンク」押下 → データが削除されることを確認  

※main.jsの「経路」の箇所で、ルーティングを設定しています。  
上記以外の経路は設定されていないため、  
「404 ...NOT FOUND...」の画面が表示されれば成功です。  

### 事前準備2  

事前準備1でcloneした「tomosta_salon」では、preuser、course、user3つのうち、preuserのみ完了しています。  
courseとuserは、モデルのみ完成、「ビュー」と「コントローラ」は空白のままです。  
preuserを参考に、courseとuserの「ビュー」と「コントローラ」の作成、「経路の追加」をしてみてください。  
途中まででOKです。無理しない範囲で楽しく作成してみてください。    
当日は、お互いが作成したコードの続きから一緒にアプリを完成しましょう。  

***
 
### 当日詳細
  
- 3つのモデル全てに対してCRUD機能を実装し、ビューからデータの新規作成/表示/更新/削除ができるようにします。  

☆以下のステップで進みます。   

1 ビューを作成する  
⇒views/preusersの4つのビューを参考に、  
views/users、views/coursesにそれぞれ4つのビューを作成する。  

2 経路を追加する  
⇒preusersを参考に、main.jsの経路の箇所にusers、coursesのルーティングを追加します。  

3 コントローラとモデルの接続  
⇒preuserモデルとpreusersコントローラの接続を参考に、  
userモデルとusersコントローラ、courseモデルとcoursesコントローラを接続します。


## Day4
### 事前準備1
* GitHubからリポジトリをクローンします。  
**ホームディレクトリ直下に**空フォルダ「lesson」を作成。  
＞ ターミナルを開く   
＞ cd lesson   
＞ git clone https://github.com/pu-chan/tomosta_salon.git

* 設定ファイル「package.json」に記述されているパッケージをインストールします。  
サーバーを立ち上げ、localhostでアクセスします。  
＞ cd tomosta_salon    
＞ npm install  
＞ npm start  

* 以下のURLにアクセスして、動作するか確認してください。  
localhost:3000  

### 事前準備2
* ユーザ登録時の「パスワードのハッシュ化」について  
- [ハッシュ](https://wa3.i-3-i.info/word16973.html)と[ソルト](https://wa3.i-3-i.info/word16974.html)とは  
⇒　localhost:3000/users/new　から、ユーザ登録を行い、mongoDBに生パスワードではなく、saltとhashが保存されているを確認する。  
⇒ 確認方法：(ターミナル) mongo > use tomosta_salon > db.users.find().pretty() > saltとhashの保存を確認。

- フラッシュメッセージについて  
⇒ ログインやユーザ登録に成功(失敗)した時に、成功(失敗)のメッセージが出るようになっています。  
⇒ userController.jsで「flash」を検索するとsuccess/errorの場合のflashメッセージを設定している箇所がヒットします。    
⇒ 好きなメッセージに変更して期待通りに動くか試してください。  


## Day5
最終回は、シンプルなチャット機能を作り、デプロイまで完成させます。  
チャット機能の実装はむずかしくありませんが、新しい概念(WebSockt)が登場します。  

### 事前準備1
* [ポーリング](https://thinkit.co.jp/story/2011/03/01/2025)、[WebSocket](https://www.sejuku.net/blog/70583)(今回使用するのはWebSocket)について理解する。  
* WebSocketをサポートするサービス[「socket.io」の使い方](https://www.sejuku.net/blog/82316)を学ぶ。  

### 事前準備2
* GitHubからリポジトリをクローンします。  
**ホームディレクトリ直下に**空フォルダ「lesson」を作成。  
＞ ターミナルを開く   
＞ cd lesson   
＞ git clone https://github.com/pu-chan/tomosta_salon.git

* 設定ファイル「package.json」に記述されているパッケージをインストールします。  
サーバーを立ち上げ、localhostでアクセスします。  
＞ cd tomosta_salon    
＞ npm install  
＞ npm start  

* 以下のURLにアクセスして、動作するか確認してください。  
localhost:3000  
