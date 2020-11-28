##### [Mishima.syk #16](https://connpass.com/event/164605/)　2020/11/28
# 「気軽に音声認識」@tkochi0603
* マイクを入力デバイスとして使えるか、音声認識を試した話。

---
# 環境
* Speech Recognition APIをChromeで試しました。(他のブラウザはまだまだ未実装みたい)
  * オンラインじゃないと動作しない ⇒ サーバに処理を丸投げしてるようです。
  * 実験的なAPIのため、未実装な機能もあるようです。
  * イントラで試す際は、Chromeはhttpsでないと動作しませんのであしからず。
    * AndroidのChromeは動作が不安定な印象です

---
# 試したこと
### サンプル1
+ 話した内容を文字列に忠実に変換できるか？
  + [https://kochi0603.github.io/mishima16/Speech2Text.html](https://kochi0603.github.io/mishima16/Speech2Text.html)
    + そのまま表示するシンプルなサンプルです。
    + [ソースコード](https://github.com/kochi0603/mishima16/blob/main/Speech2Text.html)

  + 所感
    + **ちゃんとした文章なら、長くても変換してくれました。文脈から正しい単語に補正しているようです。**
    + **短い単語や、新しい単語は変換できずに、誤変換や固まることがあります。**
    + 誤変換の修正が課題ですが、メールの文章などのちょっとした長文を書くときに使えそうです。
    + 日本語モードで実装してますが、英語モードにすると、私の発音だと全滅です。。


### サンプル2
+ 話した内容からアクションにつなげられるか？
  + [https://kochi0603.github.io/mishima16/Speech2Action.html](https://kochi0603.github.io/mishima16/Speech2Action.html)
    + 「google scholar で pain を探す」のように話すと、検索画面に飛ぶリンクを表示するサンプルです。
    + [ソースコード](https://github.com/kochi0603/mishima16/blob/main/Speech2Action.html)

  + 所感
    + 本当は、「google pain」のように単語の列挙でアクションさせたかったが、サンプル1のように文章じゃないと精度が悪かったので文章で入力するようにしました。
    + 日本語と英語の区別、短い単語（番号類）、専門用語やシステム名など、歯がゆい感じ。
    + シンプルな実装ですが、もう一工夫、ふた工夫必要です。
      + 形態素解析で、目的語や動詞を認識すれば幅が広がりそうです。


### サンプル3
+ おまけ：分子を話して描画することができるか？
  + [https://kochi0603.github.io/mishima16/Speech2Mol.html](https://kochi0603.github.io/mishima16/Speech2Mol.html)
    + SMILESを話して構造式を表示する。(こんなシチュエーションないですが。あくまで遊びです。)
    + [ソースコード](https://github.com/kochi0603/mishima16/blob/main/Speech2Mol.html)

  + 所感
    + 2重結合や3重結合とか構造が複雑になると、SMILESを音声認識させるのはやはり無理でした。


### まとめ
＊ いい点
  * 長い文章でも、正しい文章なら正しく認識してくれますね。
  * Javascriptだけで結構使い物になりました。イントラの既存のシステムと連携も容易ですし。
* いまいちな点
  * ですが、日本語と英語の区別、短い単語（番号類）、専門用語やシステム名などを、現場で使うには学習と一工夫が必要そうです。
  * この辺を解決しないと実験室で使えるようにならない。
    * 有償のデバイスやソフトを入れる？

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
   * TinySegmenter(軽量。品詞ナシ) http://chasen.org/~taku/software/TinySegmenter/
   　＊ サンプル2で実装してみた

 * electronだと50回/日の制限があるらしい(残念)
   * [https://qiita.com/akameco/items/b507d50e22b2e56e8827](https://qiita.com/akameco/items/b507d50e22b2e56e8827)

 * WindowsやMacの標準機能としての音声入力(試してないけど)
   * [https://joshi-spa.jp/1038926/2](https://joshi-spa.jp/1038926/2)

 * IBM watson（試してないけど）
   * https://www.ibm.com/jp-ja/cloud/watson-speech-to-text

---
### 以前書いた記事もぜひ
 * 画像認識をChromeで実装した話( PCのカメラを使ってQRコードを認識する例 )
   * [https://github.com/kochi0603/mishima12](https://github.com/kochi0603/mishima12)
