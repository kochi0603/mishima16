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

---
# 試したこと
+ 話した内容を文字列に変換できるか？
  + シンプルに話した内容をそのまま、表示するサンプルです。
  + https://kochi0603.github.io/mishima16/Speech2Text.html

  + (所感)
  + 長くてもちゃんとした文章なら、ちゃんと変換してくれました。文脈から正しい単語に変換するようです。 
  + ⇒⇒ 短い単語や、新しい単語は変換できずに、誤変換や固まることがあります。

+ 話した内容からアクションにつなげられるか？
  + 「google scholar で pain を探す」のような文章を話すと、検索画面に飛ぶリンクを表示するサンプルです。
  + https://kochi0603.github.io/mishima16/Speech2Action.html

  + (所感)
  + 当初は、「google pain」のように単語の列挙でアクションさせようとしましたが、文章じゃないと精度がわるいので文章にしました。

+ おまけ
  + SMILESを話して構造式を表示する(使う場面はありませんが、遊びです)
  + https://kochi0603.github.io/mishima16/Speech2Mol.html

  + (所感)
  + まぁ難しい♪

---
## 参考にしたサイト
 * Webページでブラウザの音声認識機能を使おう - Web Speech API Speech Recognition
   * https://qiita.com/hmmrjn/items/4b77a86030ed0071f548

 * SpeechRecognition( MDN )
   * https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition
