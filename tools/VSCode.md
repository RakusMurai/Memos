# VSCode設定
<!-- TOC -->

- [VSCode設定](#vscode%E8%A8%AD%E5%AE%9A)
    - [設定手順](#%E8%A8%AD%E5%AE%9A%E6%89%8B%E9%A0%86)
    - [基本設定](#%E5%9F%BA%E6%9C%AC%E8%A8%AD%E5%AE%9A)
    - [導入済み拡張機能一覧](#%E5%B0%8E%E5%85%A5%E6%B8%88%E3%81%BF%E6%8B%A1%E5%BC%B5%E6%A9%9F%E8%83%BD%E4%B8%80%E8%A6%A7)
        - [Beautify](#beautify)
        - [Code Runner](#code-runner)
        - [Debugger for Java](#debugger-for-java)
        - [ESLint](#eslint)
        - [Git History (git log)](#git-history-git-log)
        - [Java Extension Pack](#java-extension-pack)
        - [Java Language Support](#java-language-support)
        - [jQuery Code Snippets](#jquery-code-snippets)
        - [Language support for Java ™ for Visual Studio Code](#language-support-for-java-%E2%84%A2-for-visual-studio-code)
        - [Markdown All in One](#markdown-all-in-one)
        - [Markdown TOC](#markdown-toc)
        - [Project Manager](#project-manager)
        - [Settings Sync](#settings-sync)
        - [VSCode-icons](#vscode-icons)

<!-- /TOC -->

## 設定手順
基本的にはMarketPlaceからインストールを行う。  

## 基本設定
  "editor.snippetSuggestions": "top" 補完機能がローカルに優先して表示される。


## 導入済み拡張機能一覧

### Beautify
コードを見やすく整える。  
拡張機能がリリースされており、導入することで様々なファイルに対応する。

### Code Runner
コードを実行し、出力するのに使う。

### Debugger for Java
Javaのデバック機能。

### ESLint
別途Node.jsが必要。

### Git History (git log)
Git拡張機能  
コミット履歴の表示や、指定コミットへ戻すことができる。

### Java Extension Pack
Javaの必要機能を一括インストールする。  
具体的には [Language support for Java ™ for Visual Studio Code](#language-support-for-java-%E2%84%A2-for-visual-studio-code)と[Debugger for Java](#debugger-for-java)をインストール。  
導入するとうまく補完が利かなくなる時が…その場合は一度オフに。

### Java Language Support
Javaの補完機能拡張。  
インストールすることでクラスパスに含まれた依存関係のあるJarファイルの補完、インポートが可能になる。

### jQuery Code Snippets
jQueryの補完機能。  
これのためだけにVSCodeを使っているとしても過言でない。

### Language support for Java ™ for Visual Studio Code
VSCodeでJavaを触るなら必須パッケージ。  
端末内でJAVA_HOMEの変数を持っていないと使えない。 
Pathの通し方は別途。   

### Markdown All in One
MarkDown形式のコード補完をする。  v
それ以上に、MarkDownのOUTLINEが便利。

### Markdown TOC
Markdown形式の冒頭に見出しへのジャンプリンク目次を自動生成。 入れたいところで右クリック=>以上。 

### Project Manager
VSCode内でファイルをジャンプする時に活躍。  
一度ファイルを開いて、登録してけばあとは簡単に切り替え可能。

### Settings Sync
複数の端末でVSCodeを利用する際に便利。  
各端末ごとの設定を統一することができる。  
Git Hubアカウント必須。  
Git Hubプロフィール設定からGsitIDを取得し、そのIDで共有を行う。

詳しくは[Setting Sync](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync)を確認。  

### VSCode-icons
フォルダのアイコンを変える。  
見やすさ重視。


-Updated
2017.10.29