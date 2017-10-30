# MarkDown記法　VSCode対応 まとめ
<!-- TOC -->

- [MarkDown記法　VSCode対応 まとめ](#markdown%E8%A8%98%E6%B3%95-vscode%E5%AF%BE%E5%BF%9C-%E3%81%BE%E3%81%A8%E3%82%81)
    - [VSCodeの設定](#vscode%E3%81%AE%E8%A8%AD%E5%AE%9A)
    - [MarkDown記法 チートシート](#markdown%E8%A8%98%E6%B3%95-%E3%83%81%E3%83%BC%E3%83%88%E3%82%B7%E3%83%BC%E3%83%88)
        - [見出し (#)](#%E8%A6%8B%E5%87%BA%E3%81%97)
        - [改行 ("space*2")](#%E6%94%B9%E8%A1%8C-space2)
        - [リスト (*)](#%E3%83%AA%E3%82%B9%E3%83%88)
        - [番号リスト (1.)](#%E7%95%AA%E5%8F%B7%E3%83%AA%E3%82%B9%E3%83%88-1)
        - [コードブロック (space*4)](#%E3%82%B3%E3%83%BC%E3%83%89%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF-space4)
        - [引用 (>)](#%E5%BC%95%E7%94%A8)
        - [水平線 ---](#%E6%B0%B4%E5%B9%B3%E7%B7%9A)
        - [リンク ([text] (http://~))](#%E3%83%AA%E3%83%B3%E3%82%AF-text-http)
        - [強調 (****)](#%E5%BC%B7%E8%AA%BF)
        - [コード (``)](#%E3%82%B3%E3%83%BC%E3%83%89)
        - [エスケープ (`<div>`)](#%E3%82%A8%E3%82%B9%E3%82%B1%E3%83%BC%E3%83%97-div)

<!-- /TOC -->
メモエディタとしてVSCodeを利用する際のチートシートです。  
VSCodeにはデフォルト機能でmdファイルのプレビュー機能がついてます。  
* MarkDownプレビューを表示(Ctrl+Shift+v)  

## VSCodeの設定
上記のようにデフォルトでプレビューは可能ですが、より実用的になるよう拡張機能を利用します。  
VSCodeのMarketPlaceから [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one) をインストールします。  
  
この拡張機能を実装することで一部のコード補完機能(MarkDownをマスターしてると補完機能のほうが入力多いので無駄機能)とアウトライン機能が利用できます。  
アウトライン機能は見出しにそのまま飛べるのでこっちが非常に便利です。

## MarkDown記法 チートシート
### 見出し (#)
VSCode=>heading  
コード 
  
      # 見出し1
      ## 見出し2
      ### 見出し3
      #### 見出し4
      ##### 見出し5
      ###### 見出し6
### 改行 ("space*2")
改行には改行したいところで半角スペース2つ
### リスト (*)
コード

    * ABC
    * DEF
    * GHI
見た目
* ABC
* DEF
* GHI

### 番号リスト (1.)
コード  

    1. abc
    1. def
    1. ghi
見た目
1. abc
1. def
1. ghi  
### コードブロック (space*4)
VSCode=>fenced codeblock  
コードを描く場合半角スペース4つまたはタブから始める。  
見た目は上記コードを参照。
### 引用 (>)
引用先を参照、協調させるときに使う。  
コード

    > あいう
    > かきく
    > さしす
見た目
> あいう
> かきく
> さしす
### 水平線 ---
VSCode=>horizontal rule  
コード

    ---
見た目

---
### リンク ([text] (http://~))  
クリックリンクの作成

    [Google](https://www.google.co.jp/)
見た目    
[Google](https://www.google.co.jp/)
### 強調 (****)
VSCode=>bold  
コード

    **強調文字**
見た目
**強調**
### コード (``)
VSCode=>code  
インラインでコードを書きたいとき  
コード  

    見出しは`###`で表示します
見出しは`###`で表示します
### エスケープ (`<div>`)
記号文字をそのまま表示したい時  
一文字ならバックスラッシュ  
一段段落全部なら `<div>`で囲ったほうが早い

