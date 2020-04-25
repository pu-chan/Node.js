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
