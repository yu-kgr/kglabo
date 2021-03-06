+++
author = "@yu-kgr"
categories = ["TIL"]
date = "2018-01-01"
description = "2018/09 - second week I Learned | 一週間で知った事・学んだ事の個人的な備忘録"
featured = "/img/til/til.jpg"
featuredalt = "til"
featuredpath = "https://kglabo.com"
title = "2018/09 - second week I Learned"
type = "post"
draft = "false"
+++

# 今週、知った/学んだこと

<!-- tags = ["DB"] -->

## 2018/09/10- Learned

09月10日（月）のToday I Leaned.

### データベース（DB）について

RDB（リレーショナル・データベース）に関する📝  

#### 登場人物

下記はほぼ表計算ソフトの内容に近いのでそれに似た例えで記載。

>![図](/img/2018/09/160425_DBword_04.png)
> 出典元: [データベースの用語を理解しよう 「テーブル」「レコード」「カラム」「フィールド」とは？](https://academy.gmocloud.com/know/20160425/2259)

##### テーブル

シートとかブックとか呼ばれてるやつ  
基本的に複数存在していて、ECサイトなどの場合は「顧客」と「商品」などの分け方で別テーブルを作成する

##### カラム

シートの列に該当するもの  
カラム毎に属性をつける事ができる。

- 型（桁数） / 必須 / INDEX etc...

##### レコード

カラムが設定されたテーブルに入ったデータそのもの  
テーブルの複数する列に対して入れられる行のデータになる

##### フィールド

レコード（データ）を構成している1つ1つのセル（値）のこと  
複数のレコード（データ）の同じフィールド（値）を集めたものがカラム（列）になる

つまりDBテーブルとは、

- 複数のカラムが用意されたテーブルに対して、レコードが記録されるもの

で、RDBは上記を別のテーブルと関連づける事で  
データを複数の表として管理して表と表の間の関係を定義する事でデータの関連性を扱えるようにするもの。

#### flyway

- DBのマイグレーションフレームワーク
- DBのマイグレーションとは「SQLの変更を差分SQLファイルとしてバージョン管理するしくみ」
  - 最新の状態すべてが反映された状態をバージョン管理するわけでなく、DBに対して適用可能な状態のSQLファイル差分を管理する

##### DDL

- Data Definition Language / データ定義言語
- DBにおけるデータ構造を定義するために用いられる言語のこと。

#### DBのデータモデリングについて

- TODO: 後々ちゃんと学ぶ
  - [参考:【DB設計入門|ER図|MySQL】コンビニレシートから学ぶ！データモデリング手法](https://engineers.weddingpark.co.jp/?p=662)

1. 概念設計
  a. 実態・関連図（ESR図）
  b. 正規化
2. 論理設計
  a. 正規化・非正規化検討
  b. インデックス設計
3. 物理設計
  a. パフォーマンス・チューニング

## 2018/09/11- Learned

09月11日（火）のToday I Leaned.

「[手を動かしながら2週間で学ぶ AWS 基本から応用まで](https://www.udemy.com/aws-14days/)」  
Day3 - VPCを使ってネットワークを構築する

### VPCを作る

- public サブネット
- Internet GWも一緒に作成する

### Webサーバ用 EC2の作成

- VPCやサブネットを指定

### Webサーバ用 EC2の設定

- OS初期設定
- ミドルウェアのインストール
- Githubに用意しているサンプルコードを動かす


### MEMO: sshでec2に入ろうとしたらErrorが出た

```shell
$ ssh -i ~/.ssh/***.pem ec2-user@***.***.***.***
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0444 for '/Users/NAME/.ssh/***..pem' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "/Users/NAME/.ssh/***..pem": bad permissions
ec2-user@***.***.***.***: Permission denied (publickey,gssapi-keyex,gssapi-with-mic).
$ chmod 0600 ~/.ssh/***.pem
$ ssh -i ~/.ssh/***.pem ec2-user@***.***.***.***
```

- Permissionを0600にしてあげないとだめっぽい
- `$ chmod 0600 ~/.ssh/***.pem` で変更してあげたら問題なく行けた。

### 職種を超えた交流の為の文書明文化

こちらの記事の内容がとても参考になったので 📝
- [参考:職種を超えたコミュニケーションデザインを考える](https://yasuhisa.com/could/article/howto-work-with-designers/)

#### keyword: コンテンツモデル
>コンテンツタイプは様々な項目によって構成されていますが、それを視覚化するプロセスをコンテンツモデルといいます。コンテンツモデルは以下のようにダイアグラムとして表現されることが多いです。
>![コンテンツモデルのダイアグラム図](http://yasuhisa.com/could/wp-content/uploads/2015/09/content-model-examples.png)
> 出典元: [コンテンツモデルの基礎と活用メリット](http://yasuhisa.com/could/article/content-model/)

#### keyword: ユーザ行動（CTA）

>行動喚起要素CTA (Call To Action)
>CTAとは「Call To Action (コール・トゥ・アクション)」の略で、「行動喚起」のこと。WebサイトやWebマーケティングにおいては、ユーザーにアクションを促すリンクなどの「行動喚起要素」を指します。訪問ユーザーをコンバージョンに転換させるための重要な「お声掛け」要素の一つです。
>出典元: [行動喚起要素CTA (Call To Action) の基本のキホン](https://cinci.jp/blog/20180326-cta-call-to-action)）

#### keyword: モデルとユーザを考慮したデザインの作成

>サイトマップのような全体構造ではなく、画面ひとつひとつにあるコンテンツが何かを小さな要素まで切り取って整理する
>ページという概念から一度切り離してコンテンツについて考えるのがコンテンツモデル
>![ブログの例](https://yasuhisa.com/could/wp-content/uploads/2017/01/blog-contentmodel.png)
- 出典元: [コンテンツモデルからデザインシステムを作り出す](https://yasuhisa.com/could/article/content-model-pattern/)

3. 人によって言葉・物事の捉え方が様々

#### アンチパターン

1. 「これどうですか」は危険信号
2. センス・好み・偉い人が決める
3. 後戻り、迷走の原因になる

#### 内容の文書明文化（例）

1. 課題解決へ議論をシフトさせる
2. デザインの経緯を記録する
3. 文書の定型化を心がける

項目 | 詳細・内容
---|---
🔎 調査で得たニーズ | Cell A-2
🏢 その他課題 | ビジネス、開発から出た課題
🗒 仮説 | デザインが解決すべき問題は何か
⚖ 指標 | KPI/UX指標
🎨 デザイン案 | メリット、デメリット、リスク
🔨 修正項目 | フィードバック
▶ 次のアクション | 次にやること
🎫 Issueへのリンク | プロジェクト管理と情報連携
🖼 画面 | 現状の把握
👨 ユーザーコンテキスト | 画面表示までの背景
🚩 変更の目的 | デザイン原則やユーザビリティ
✏️ 変更案 | どこを変え、なぜ変えるか

### ワークフロー

項目 | 詳細・内容
---|---
1. コンセプト | ユーザー像・課題・プロダクト価値の共有ができているか
  a. 要件定義 | ユースケースを業種を超えて共有されているか
  b. 助っ人 | 広くアイデアを集める場は用意されているか
2. プロトタイプ | 検証できるツールやチャネルが用意されているか
3. テスト | -
4. レビュー | 前提に基づいてファシリテーションできているか
5. ビジュアルデザイン | どう連携を取っていくか
6. インタラクションデザイン |     〃

## 2018/09/13- Learned

09月13日（木）のToday I Leaned.

### データベース

#### テーブル作成時に考える事

テーブル作成を行う際に決めておく事は、

1. 物理名の決定
2. 型の決定
3. 主キーの決定
4. NULLの決定

となる。

##### 物理名の決定

- 日本語の表現は論理名（テーブル内に名称として存在していないもの）
- 英語の表現は物理名（テーブル内に名称として存在しているもの）

##### 型の決定

表現するデータが文字なのか数字なのか。
   
- 文字であれば、精度（長さ）を決める必要がある
- 数字であれば、INT、FLOATなどを決める必要がある。

##### 主キーの決定

データの一意に決定できるデータのことを主キー（Primary Key: PK）と呼ぶ。  
類似したものとして外部キー（Foreign Key: FK）も存在する

>「一意」は「意味や値が一つに確定していること。」
> 会員番号、運転免許証番号、クレジットカード番号などがあります。ただし、氏名は同姓同名が存在する可能性があるため、一意とはなりません。基本的に一意となる情報は、氏名や商品名など人間が判断して付けた名前ではなく、機械的に付けた番号やコードになります。
> 出典元: [データが「一意となる」とは：そのデータが”ユニーク”だと言い切るための「キー」があること｜データ分析用語を解説](https://www.graffe.jp/blog/533/)

##### NULLの決定

データがNULLでもよいかどうかを決める。


#### 論理削除と物理削除

##### 論理削除

- 実際にはデータは削除しない。
- 削除されたというフラッグを絡むで設定する事でユーザには削除しているように振る舞う。
  - 属に言う「フラグが立った」的なやつ

メリットとしては、  
データの復元が可能。物理削除と比べて処理即時が早い。

デメリットとしては、  
データベースにNULLとしていうデータを作りたくない（対策:[データベースを使ったデータ分析はNull(ヌル)に気を付ける | データ分析のお作法](https://www.graffe.jp/blog/2686/)）
where句での絞り込み検索を行うときにフラッグの条件を追加する必要がある。

##### 物理削除

- 実際にSQLでDeleteされる / データベースからも削除される
  - 復元したり削除されたデータを参照する事はできない

## 2018/09/14- Learned

09月14日（金）のToday I Leaned.

### MySQL

MySQLは文字コードとソートの順をもっているので、  
どの文字コードを利用して、どうソートするの？みたいな事を考える必要がある。

#### CharacterSet（文字コード）について

- 4バイト文字が普及してきている関係でMySQLに対して4バイト文字に対応した文字コードを選択する必要が出てきている。
  - 絵文字やマイナーな文字（第3・4水準漢字）など
- charsetの指定に関しては、個別に指定可能。

|変数名|説明|
|---|---|
|character_set_client | クライアント側で発行したsql文はこの文字コードになる|
|character_set_connection | クライアントから受け取った文字をこの文字コードへ変換する|
|character_set_database | 現在参照しているDBの文字コード|
|character_set_results | クライアントへ送信する検索結果はこの文字コードになる|
|character_set_server | DB作成時のデフォルトの文字コード|
|character_set_system | システムの使用する文字セットで常にutf8が使用されている|

基本的には`utf8mb4`一択らしく、すべて揃えたほうが良いらしい。

#### ソート順（Collate）について

直訳すると照合。文字コード毎の照合手順を定義するやつ  
比較する際は、文字コードだけではなくソート順が一致するかどうかを比較する。

`Collationの命名規則は "文字コード_言語名_比較法"`

- 文字コードは `utf8` とかのアレ
- 言語名は `japanese`とか`general`, `unicode`など
  - `general`や `unicode`はマルチリンガル
- 比較法は `_ci` / `_cs` / `_bin` がある
  - `_cs` : 大文字/小文字区別なし
  - `_cs` : 大文字/小文字区別あり
  - `_bin` : バイナリ

|utf8mb4で指定できるCollation|文字|区別するかどうか|
|---|---|---|
|utf8mb4_general_ci| A = a <br> 🍣 = 🍺 <br> は≠ぱ≠ば| 区別しない <br> 区別しない <br> 区別する|
|utf8mb4_unicode_ci| A = a <br> 🍣 = 🍺 <br> は≠ぱ≠ば | 区別しない <br> 区別しない <br> 区別しない |
|utf8mb4_unicode_520_ci| A = a <br> 🍣 = 🍺 <br> は≠ぱ≠ば | 区別しない <br> 区別する<br> 区別しない |
|utf8mb4_bin| A = a <br> 🍣 = 🍺 <br> は≠ぱ≠ば | 区別する <br> 区別する <br> 区別する|


区別する/しないによって、where句やソート順で影響が出る。  
要件によるが `utf8mb4_general_ci` / `utf8mb4_bin` あたりが候補になるらしい。  

## 今週の感想

- 今週も割とサーバサイド寄り / バックエンドに関する内容が多かった感じ。
