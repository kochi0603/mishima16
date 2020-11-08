##### [Mishima.syk #16](https://connpass.com/event/164605/)　2020/11/28
# 「気軽に音声認識」@tkochi0603
* 最近、Web会議が多くなり、PCのマイクをONにする機会が増えました。
* マイクを入力デバイスとして使えるか、音声認識を試しました。
  * デスクワーク
  * 実験室で手袋してる現場
  * タブレットでキーボードが面倒な状況

---
# 環境
* Speech Recognition APIをChromeで試しました。(他のブラウザはまだまだ未実装みたい)
  * オンラインじゃないと動作しない ⇒ サーバに処理を丸投げしてるようです。
  * 実験的なAPIのため、未実装な機能もあるようです。
  * イントラで試す際は、Chromeはhttpsでないと動作しませんのであしからず。

---
# 試したこと
### サンプル1
+ 話した内容を文字列に忠実に変換できるか？
  + そのまま表示するシンプルなサンプルです。
  + [https://kochi0603.github.io/mishima16/Speech2Text.html](https://kochi0603.github.io/mishima16/Speech2Text.html)

  + 所感
    + 長くてもちゃんとした文章なら、ちゃんと変換してくれました。文脈から正しい単語に変換するようです。 
      + 短い単語や、新しい単語は変換できずに、誤変換や固まることがあります。
    + 誤変換の修正が課題ですが、メールの文章などのちょっとした長文を書くときに使えそうです。
    + 日本語モードで実装してますが、英語モードにすると、私の発音だとほぼ全滅です。。


### サンプル2
+ 話した内容からアクションにつなげられるか？
  + 「google scholar で pain を探す」のように話すと、検索画面に飛ぶリンクを表示するサンプルです。
  + [https://kochi0603.github.io/mishima16/Speech2Action.html](https://kochi0603.github.io/mishima16/Speech2Action.html)

  + 所感
    + 当初は、「google pain」のように単語の列挙でアクションさせようとしましたが、文章じゃないと精度がわるいので文章で入力するようにしました。
    + 疾患名など専門用語も思いのほか正しく認識してくれます。
    + シンプルな実装ですが、仕事につかえそうな場面がありそうですね。
      + 形態素解析すればもっと別の活用方法もあるかもしれません(形態素解析のkuromoji.jsはファイルが大きいのが難点)


### サンプル3
+ おまけ
  + SMILESを話して構造式を表示する。(こんなシチュエーションないですが。あくまで遊びです。)
    + 複雑な分子を話して作ることができるか？
  + [https://kochi0603.github.io/mishima16/Speech2Mol.html](https://kochi0603.github.io/mishima16/Speech2Mol.html)

  + 所感
    + 2重結合や3重結合とか構造が複雑になると、SMILESを音声認識させるのはやはり無理でした。


---
### 参考にしたサイト
 * Webページでブラウザの音声認識機能を使おう - Web Speech API Speech Recognition
   * このページを参考に自分で解釈しながら書き換えました。
   * [https://qiita.com/hmmrjn/items/4b77a86030ed0071f548](https://qiita.com/hmmrjn/items/4b77a86030ed0071f548)

 * SpeechRecognition( MDN )
   * [https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition](https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition)

 * 形態素解析(Kuromoji.js)を使うともっと面白そうです。
   * Kuromoji を使ってブラウザ上で形態素解析を行う (Reactあり/なし) @Qiita
     * [https://qiita.com/torao@github/items/45ad9640cf94d3169cae#react-%E3%82%92%E4%BD%BF%E3%82%8F%E3%81%AA%E3%81%84%E6%96%B9%E6%B3%95](https://qiita.com/torao@github/items/45ad9640cf94d3169cae#react-%E3%82%92%E4%BD%BF%E3%82%8F%E3%81%AA%E3%81%84%E6%96%B9%E6%B3%95)

 * electronだと50回/日の制限があるらしい(残念)
   * [https://qiita.com/akameco/items/b507d50e22b2e56e8827](https://qiita.com/akameco/items/b507d50e22b2e56e8827)

 * WindowsやMacの標準機能としての音声入力もありますよ。
   * [https://joshi-spa.jp/1038926/2](https://joshi-spa.jp/1038926/2)

---
### 以前書いた記事もぜひ
 * 画像認識をChromeで実装した話( PCのカメラを使ってQRコードを認識する例 )
   * [https://github.com/kochi0603/mishima12](https://github.com/kochi0603/mishima12)
