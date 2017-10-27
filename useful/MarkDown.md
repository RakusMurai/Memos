# MarkDown記法　VSCode対応 まとめ

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

