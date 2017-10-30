# PlayFramework導入
## 目次
<!-- TOC -->

- [PlayFramework導入](#playframework%E5%B0%8E%E5%85%A5)
    - [目次](#%E7%9B%AE%E6%AC%A1)
    - [導入環境](#%E5%B0%8E%E5%85%A5%E7%92%B0%E5%A2%83)
    - [導入手順](#%E5%B0%8E%E5%85%A5%E6%89%8B%E9%A0%86)
        - [フレームワークのダウンロード](#%E3%83%95%E3%83%AC%E3%83%BC%E3%83%A0%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%AE%E3%83%80%E3%82%A6%E3%83%B3%E3%83%AD%E3%83%BC%E3%83%89)
        - [Pathの設定(Java)](#path%E3%81%AE%E8%A8%AD%E5%AE%9Ajava)
        - [Pathの設定(PlayFramework)](#path%E3%81%AE%E8%A8%AD%E5%AE%9Aplayframework)
    - [PlayFrameworkの開始](#playframework%E3%81%AE%E9%96%8B%E5%A7%8B)
        - [アプリケーションの作成](#%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E4%BD%9C%E6%88%90)
        - [エラーメッセージ回避](#%E3%82%A8%E3%83%A9%E3%83%BC%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8%E5%9B%9E%E9%81%BF)
        - [Eclipseプロジェクトに変更](#eclipse%E3%83%97%E3%83%AD%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E3%81%AB%E5%A4%89%E6%9B%B4)
        - [アプリケーションの初回実行](#%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E5%88%9D%E5%9B%9E%E5%AE%9F%E8%A1%8C)
        - [アプリケーションの実行](#%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E5%AE%9F%E8%A1%8C)
    - [PlayFrameworkの編集](#playframework%E3%81%AE%E7%B7%A8%E9%9B%86)
        - [Controller](#controller)
        - [View](#view)
        - [route](#route)
    - [データのやり取り](#%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E3%82%84%E3%82%8A%E5%8F%96%E3%82%8A)
        - [コントローラの準備](#%E3%82%B3%E3%83%B3%E3%83%88%E3%83%AD%E3%83%BC%E3%83%A9%E3%81%AE%E6%BA%96%E5%82%99)
        - [HTML](#html)
            - [@helper](#helper)
        - [コントローラの受け取り](#%E3%82%B3%E3%83%B3%E3%83%88%E3%83%AD%E3%83%BC%E3%83%A9%E3%81%AE%E5%8F%97%E3%81%91%E5%8F%96%E3%82%8A)
    - [DB](#db)
        - [Ebean](#ebean)
        - [application.conf](#applicationconf)
        - [bulid.sbt](#bulidsbt)
        - [project/plugins.sbt](#projectpluginssbt)
    - [debug](#debug)
    - [設定完了](#%E8%A8%AD%E5%AE%9A%E5%AE%8C%E4%BA%86)

<!-- /TOC -->
## 導入環境
Windows10  
jdk1.8.0_151
PlayFramework2.6.X
VScode

## 導入手順

### フレームワークのダウンロード
[公式ホームページ](https://www.playframework.com/)のGET THE LATEST PACKAGEが最新版ダウンロードリンク。  
Download a starter project => zipをクリックでダウンロードする。  
ダウンロード後適当なフォルダに解凍する。

### Pathの設定(Java)
環境変数JAVA_HOMEおよびPath(Java/bin)必要。  
導入は割愛。

### Pathの設定(PlayFramework)
解凍したフォルダにあるBinファイルへアクセスできるようパスを通す。  
Windowsのシステムから環境変数に追加する。(C:/解凍先フォルダパス/bin)  
Pathを設定することでコマンドラインから実行できるようになる。

## PlayFrameworkの開始

### アプリケーションの作成
任意のフォルダに移動。  

    cd C:/ワークスペース    
Playアプリケーションを作成する。

    activator new アプリケーション名
このアプリケーション名でフォルダを作成する。  
作成中に利用するテンプレートを聞かれるのでplay-javaを選択。  
コマンドラインが入力待機になればPlayアプリケーションが作成される。  
作成したアプリケーションに移動。

    cd C:/アプリケーション名

### エラーメッセージ回避
Windowsのsbtスクリプトは、sbtconfig.txtを利用していない(詳しくはわかりません)らしく新規作成したアプリケーションを実行すると

    ファイル BIN_DIRECTORY\..\conf\sbtconfig.txt が見つかりません。
というエラーメッセージ表示されてしまう。  
そのためactivotar解凍ファイルの中に\conf\sbtconfig.txtを作成する。

    code 解凍先フォルダパス\conf\sbtconfig.txt
編集内容　sbtconfig.txt

    -Dinput.encoding=Cp1252
    -Xmx512M
    # -XX:MaxPermSize=256m
    -XX:ReservedCodeCacheSize=128m
    # Set the extra SBT options
    -Dsbt.log.format=true
で保存。
エラーメッセージを回避できる。
referenceフォルダに保存。

※やらなくても問題ないが気持ち悪いので

### Eclipseプロジェクトに変更
Javaフォルダを一つのプロジェクトとして認識させるために.settingフォルダが必要。  
activatorのEclipseプロジェクト化機能を利用。
plugins.sbtを編集

    code アプリケーション名/project/plugins.sbt
編集内容 (plugins.sbt)

    addSbtPlugin("com.typesafe.sbteclipse" % "sbteclipse-plugin" % "5.2.3")
バージョンは[sbteclipse](https://github.com/typesafehub/sbteclipse)のlatest versionを参照。  

build.sbtを編集

    code アプリケーション名/build.sbt
編集内容 (build.sbt)

    EclipseKeys.preTasks := Seq(compile in Compile)
    EclipseKeys.projectFlavor := EclipseProjectFlavor.Java
    // Java project. Don't expect Scala IDE
    EclipseKeys.createSrc := EclipseCreateSrc.ValueSet(EclipseCreateSrc.ManagedClasses, EclipseCreateSrc.ManagedResources)
    // Use .class files instead of generated .scala files for views and routes 
1行目=>activoter eclipseコマンドの実行前にcomplieを実行する設定。
2行目=>activoter eclipseコマンドの実行時にscalaを使わない設定。
3行目=>activoter eclipseコマンドの実行時にsrcフォルダを作成する設定。Scalaを使わないときに設定。  

### アプリケーションの初回実行
アプリケーションフォルダ直下に移動し、以下コマンドでPlayフレームワークを実行する。  

    activator
Playコンソールが起動する。
上記設定を読み込むため

    eclipse with-source=true
を実行する。  
実行することで.settingファイルができるので、Playアプリケーションが一つのアプリケーションとして認識される。  
そのため任意のIDEでeclipseプロジェクトとしてインポートが可能。

### アプリケーションの実行
Playコンソールで

    run
でアプリケーションの実行。
http://localhost:9000でトップに移動する。

## PlayFrameworkの編集
MVCアーキテクチャ。  
不要なカプセル化を避ける方向で、変数もpublicで持つことが多い。  
privateだとgetter,setterを用意する分コードが冗長になることを避ける。  
App/viewsにviewsが、App/CotrillersにControllerクラスができている。  
Modelは自分で作成していく。

### Controller
App/Controllersに
* AsyncController.java
* CountController.java
* HomeController.java
 
がデフォルトで用意されている。  
コントローラはplay.mvc.Controllerクラスを継承することで宣言される。  
returnはplay.mvc.viewのokメソッドでResult型で返す。  
このリターンでHTMLが呼ばれるようになる。  
Result型には、アクセスの成否、エラーメッセージ、HTMLなどが入力される。  
ok(Htmlのファイル名.render(Htmlファイルに渡すオブジェクト));  

※okメソッドの文法エラーはPlayは実行時にコンパイルを行い、引用元のメソッドを変更するため、開発中は警告が出る。  
コンパイル後は引数が変更されたメソッドがコンパイルされているのでエラーがなくなる。

### View
App/Viewsに
* index.scala.html
* main.scala.html

がデフォルトで用意されている。
mainを読み込むことでアプリケーションの全ページの共通設定が可能。  
(Controller=>個別html=>mainHtml)  
個別Htmlでは@main(String,{})でメインを呼び出す。  
Stringはページタイトル、｛｝の中にHtml情報を渡すことでページが表示される。  

@routes.Assets.versioned()でpublicフォルダを呼び出す。  
()の中にpublic以下のパスを記載することで、アクセスできる。  
js、cssファイル等はここに保存。  

ページ上部@(変数名:オブジェクト型)(変数名:オブジェクト型)…
で変数名でオブジェクトを受け取る。  
@変数名で表示する。  
Controllerから送られた順番にオブジェクトを受け取る。  
送った数と受け取った数が違うとエラー。  
送った順番で受け取らないとエラー。  
基本構文はラッパー型で送らないとエラー。

### route
conf/routeファイルでリクエストマッピング

    GET  /  controllers.Controller名.index
でgetリクエスト、「/」が来たらコントローラ名クラスのindexメソッドが呼ばれる。

## データのやり取り
### コントローラの準備
play.data.Form<T>クラスをフィールド変数に持つ。  
@Injectをつけたコンストラクタ(play.data.FormFactory
)を作り、フィールド変数に代入。

    private Form<SampleForm> form;
    @Inject
    public Application(FormFactory formFactory) {
        this.form = formFactory.form(SampleForm.class);   
    }
これでアプリケーション起動時にフォームオブジェクトが生成される。  
このフィールド変数をRenderの引数に入れてフォワードすると、入力可能になる。

    public Result index() {
        return ok(index.render("何か書いて", form));
    }

### HTML
@(form:Form[Application.sampleForm])でフォームクラスを受けとる。  
通常のHTMLタグを利用してform、inputを作成。  
formオブジェクトのプロパティ名がinputタグのname属性。

#### @helper
以下のコードをHTMLに記入すると自動でformを作成してくれる。

    @helper.form(action=routes.Application.send){@(helper.inputText(form("message") ))<input type="submit"> } }
@helper.form(action=routes.・・・)=>送信先。  
@helper.inputType(form("message"))=>inputTypeでinputのType属性、かっこの中でフォームのプロパティを指定。  
簡単なものなら生成できるが、プロパティ名の消し方不明のため、タグで書いたほうが早い。

### コントローラの受け取り
フィールド変数のplay.data.Form<T>クラスのbindFromRequest().get()メソッドを使うとリクエストに含まれるデータを受けとれる。  
get()の受け取りはフィールド変数Form<T>のT型。  
    public Result send() {
        SampleForm sampleForm = form.bindFromRequest().get();
        return ok(index.render(sampleForm.getMessage(), form.fill(sampleForm)));
    }
Form<T>のfill(T)を渡すと、フォームの中にあらかじめデータを入れて送信できる。  

## DB
### Ebean
DBアクセスを楽にしてくれる機能。  
DB設定と同時に導入していく。

### application.conf
デフォルト340行目～（不要行削除）
    
    db {
      #default.driver = org.h2.Driver
      #default.url = "jdbc:h2:mem:play"
      #default.username = sa
      #default.password = ""
      #default.logSql=true
    }
の部分にDBアクセス先情報を入力していく。  
まずは#を外してコメントアウトを解除する。  
PostgreSQL用

    default.driver = org.postgresql.Driver
    default.url = "jdbc:postgresql://ホスト名:ポート番号/DB名"
    default.username = ユーザ名
    default.password = "パスワード"
    default.logSql=true
1行目=>PostgreSQLドライバの指定。  
2行目=>DBサーバの指定。  
3行目=>サーバアクセスのユーザ名。  
4行目=>サーバアクセスのパスワード("")。   
5行目=>sqlのLogの保存設定。

db{}の下に
    ebean.default = ["models.*"]
を追加。ebeanの検索フォルダを指定する。  
ebeanについては後述。

### bulid.sbt

    lazy val myProject = (project in file(".")).enablePlugins(PlayJava, PlayEbean)
に変更(PlayJavaの後に「, PlayEbean」を追加)。  

    libraryDependencies ++= Seq(javaJdbc,cache,javaWs)   
でアプリで使用している項目を指定できる。  
postgreSQL用

    libraryDependencies++= Seq(... ,
        evolutions,
        "org.postgresql" % "postgresql" % "42.1.4"
    )
を追加。
MVN-Repojitoryで必要ソフト(今回はPostgreSQLの最新版)を検索。  
SBTタブのlibraryDependenciesの｛｝の中を上記のようにコピペ  
または、libraryDependencies+=全体を上記コードの下に追加する。  
追加するとコンパイル時に必要Jarファイルを自動でダウンロードしてくる。

### project/plugins.sbt

    addSbtPlugin("com.typesafe.sbt" % "sbt-play-ebean" % "3.2.0")
を追加(コメントアウトされているものを外すでもOK）。
3.2.0が現状一番安定している。  
不用意にVersionをあげてもエラーをはく。  
3時間以上はまりました。

ソースコードを編集する前に

    clean  
    eclipse
を実行し、IDEを再起動する。

## debug
デバックモードでの起動方法。

    cd ~/アプリケーション名
    activator activator -jvm-debug 9999 run
を実行。デバックモードで立ち上がる。  
VSCodeのデバックバーを表示し、launch.jsonをデバックバー上部からlaunch.jsonを編集。  
launch.josn

    "configurations": [
        {
            "type": "java",
            "name": "Debug (Attach)",
            "request": "attach",
            "hostName": "localhost",
            "port": 9999
        }
    ]
port9999がデバックポートになっており、ブレイクポイントに対応できるようになる。  
追加したデバックモードでVSCodeのデバックを実行すると、デバックができる。

## 設定完了
ここまで導入すると、インストールから実行、フォームの受け取り、DB設定が完了する。