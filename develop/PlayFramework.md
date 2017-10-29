# PlayFramework導入手順

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
そのためアプリケーションの中に\conf\sbtconfig.txtを作成する。

    code アプリケーション名\conf\sbtconfig.txt
編集内容　sbtconfig.txt

    -Dinput.encoding=Cp1252
    -Xmx512M
    # -XX:MaxPermSize=256m
    -XX:ReservedCodeCacheSize=128m
    # Set the extra SBT options
    -Dsbt.log.format=true
で保存。
エラーメッセージを回避できる。

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

### アプリケーションを実行
アプリケーションフォルダ直下に移動し、以下コマンドでPlayフレームワークを実行する。  

    activator
Playコンソールが起動する。
設定を読み込むため

    eclipse
を実行する。








