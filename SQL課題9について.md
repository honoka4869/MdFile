<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/9.15.10/styles/vs2015.min.css">
<link href="https://sgwp.xyz/Content/github.css" rel="stylesheet">
<link href="https://sgwp.xyz/Content/md2.css" rel="stylesheet"></link>
<script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/9.15.10/highlight.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/highlightjs-line-numbers.js@2.8.0/dist/highlightjs-line-numbers.min.js"></script>
<script>hljs.initHighlightingOnLoad();</script>
<script>hljs.initLineNumbersOnLoad();</script>

:::spoiler{#heading-link .divName}
作成日 2021/01/17  
作成者 VLB 小野 裕己
:::

# SQL課題9について

## <span>1</span>提出物

SQLite課題9の提出物についてですが、  
良くある再提出の理由の一つが提出物自体の間違いです。

> 下記DB定義を元にDDLを作成してください。

と書かれています。
:::spoiler{#heading-link .warningDiv}
※その為SQLiteを操作して作ったデータベースファイルだったり画像ファイルだったりすると提出物の間違いで再提出となります。  
:::

では、DDLとは何か？となるのが普通だと思います。  
プログラミングをしていなければ、DDLなんて聞くことなんて無いと思います。  
では、次でDDLについて説明致します。

## <span>2</span>DDLとは

DDLとは、簡潔に言いますと、SQLにわたすコード「**SQL文**」を纏めたテキストファイルの事です。  
実際に現場へ出ると自分だけの環境だけではなく、ほかの人の環境へ同じテーブル環境を用意しないと行けない状況に直面する事もあります。  
その際に、その時その時でSQL文を書いてたら時間のロスに繋がります。  
これが、自分ともうひとりならまだ良いかも知れません。  
ですが、テーブル数が多かったりした場合全てのテーブルの作成を一回一回コードを書いている暇が、あれば他の事をしたいと思うのが人です。

そこで、使用するのがDDLです。  
作成するテーブルの「**CREATE TABLE**」を全てテキストファイルに書いて保存し、それをSQLに呼び込む事でSQLがDDLの内容にそってテーブルを作成してくれます。

他にもDMLはやDCLと言った物もありますが、書き込むテーブル文によって呼ぶ方が変わってきます。  
今回はDDLだけ覚えておけばいいので、他は頭の片隅にでも入れておいてください。


まず、課題9まで進んでいるということはSQL文に触れてきたと思います。  
そこで課題9が求めているSQL文は「**CREATE TABLE**」です。

課題9のページには以下の4つのテーブル情報があります。

- 会社情報
- 社員情報
- 社員状況
- ログイン情報

この4つのテーブルを作成する為の「**CREATE TABLE**」を纏めたテキストファイルを作成し提出してください。

## <span>3</span>提出する際の注意点

テキストファイルを作成し提出してください。と言いましたが、ただ書いて出せば良いという訳ではありません。  
幾つか注意点があります。  
注意点は、下記に纏めました。

1. 予約語は全て大文字にすること
1. 1カラム毎に改行すること
1. インデントをしっかりとすること
1. 作成した後は自分で動かしてしっかりと事業部サイトに書かれている定義通りにテーブルが作成されているかを確認する
1. コメントを書くこと([SQLiteのコメントの付け方](https://www.dbonline.jp/sqlite/ini/index3.html))
1. 作成したテキストファイルの拡張子は「**.sql**」または、「**.ddl**」にして提出する

1の予約語とはSQLでテーブル名や、カラム名に使用する事が出来無い文言の事を言います。  
「**CREATE TABLE**」だったり「**DEFAULT**」だったりですね。  
後は「**INT**」とか、「**TEXT**」なども予約語です。

2、3、5については、[コーティング規約について](https://sgwp.xyz/md/コーティング規約について)にも書いた可読性に繋がります。  
可読性があがるということは他の人が内容を理解するのに時間をかけなくてすみます。

4については、これは提出する前にする事を徹底してください。  
これはSQLだけではなくプログラミングをする上でもそうです。  
作成して提出したからと言って動作しない物だと意味がありません。  
動く事はしっかりと確認しましょう。  
動作のチェックは以下の様にしてみてください。
ファイル名やパスなどは環境によって違いますので、ご自身の環境に合わせて変えてください。
```
sqlite3.exe myfriend < file.sql
sqlite3.exe myfriend
.schema
```
実際にコマンドプロンプトで行った画像が以下になります。

![イメージ](https://drive.google.com/uc?export=view&id=1KNeM1NYpAmrdr1s0S_7bKcqEX7wx3adu)

定義の間違いなどは在ってはいけませんが、人間です。 そこは仕方が有りません。  
それを見つけて指摘するのが、我々添削者の仕事です。  
少しずつ自分で見つけられる様にして行きましょう。

6については、DDLを書いてあるテキストファイルですよと他の人に教える事が出来ます。  
基本は、「**.sql**」にすると良いでしょう。  

5、6については、やっていなくても指摘はされることはあっても、それで再提出という事は無いと思いますが、意識しておきましょう。
