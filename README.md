##### [Mishima.syk #16](https://connpass.com/event/164605/)　2020/11/28
# 「気軽に音声認識　@tkochi0603」
* 在宅勤務でWeb会議が多くなり、ヘッドセットを付ける機会が増えましたね。
* せっかくなのでマイクを使って音声認識してみました。
  * 入力手段として使いものなるでしょうか？

---
# 環境
* Chromeで試しました。(他のブラウザは不完全)
  * Speech Recognition API
    * オンラインじゃないと動作しない ⇒ サーバに処理を丸投げしてるようです。
    * 実験的なAPIのため、未実装な機能もあるようです。
  * イントラで試す際、httpsでないと動作しませんのであしからず。
    * Edgeなら、httpでも動作するそうです。

---
# 試したこと
### サンプル1
+ 話した内容を文字列に変換できるか？
  + 話した内容をそのまま、表示するシンプルなサンプルです。
  + https://kochi0603.github.io/mishima16/Speech2Text.html

  + (所感)
    + 長くてもちゃんとした文章なら、ちゃんと変換してくれました。文脈から正しい単語に変換するようです。 
    + ⇒⇒ 短い単語や、新しい単語は変換できずに、誤変換や固まることがあります。

### サンプル2
+ 話した内容からアクションにつなげられるか？
  + 「google scholar で pain を探す」のように話すと、検索画面に飛ぶリンクを表示するサンプルです。
  + https://kochi0603.github.io/mishima16/Speech2Action.html

  + (所感)
    + 当初は、「google pain」のように単語の列挙でアクションさせようとしましたが、文章じゃないと精度がわるいので文章にしました。
    + シンプルな実装ですが、仕事につかえそうな場面がありそうですね。
      + 形態素解析して別の活用方法もあるかもしれませんね。(形態素解析のkuromoji.jsはファイルが大きいのが難点)

### サンプル3
+ おまけ
  + SMILESを話して構造式を表示する。(使う場面はありませんが、遊びです)
    + 複雑な分子を話して作ることができるか？
  + https://kochi0603.github.io/mishima16/Speech2Mol.html

  + (所感)
    + 難しい♪ かっこもあるし、2重結合や3重結合とか、音声認識には向いてませんね。

---
### 参考にしたサイト
 * Webページでブラウザの音声認識機能を使おう - Web Speech API Speech Recognition
   * https://qiita.com/hmmrjn/items/4b77a86030ed0071f548

 * SpeechRecognition( MDN )
   * https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition

 * 形態素解析(Kuromoji.js)を使うともっと面白そうです。
   * Kuromoji を使ってブラウザ上で形態素解析を行う (Reactあり/なし) @Qiita
     * https://qiita.com/torao@github/items/45ad9640cf94d3169cae#react-%E3%82%92%E4%BD%BF%E3%82%8F%E3%81%AA%E3%81%84%E6%96%B9%E6%B3%95

---
### 以前書いた記事もぜひ
 * 画像認識をChromeで実装した話( PCのカメラを使ってQRコードを認識する例 )
   * https://github.com/kochi0603/mishima12
