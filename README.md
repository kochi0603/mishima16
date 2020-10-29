##### [Mishima.syk #16](https://connpass.com/event/164605/)　2020/11/28
# 「気軽に音声認識　@tkochi0603」
* 在宅勤務でWeb会議が多くなり、ヘッドセットを付ける機会が増えました。
* 音声認識を使って遊んでみました。
  * 手を使えない環境での入力手段として使いものなるといいですが。。

---
# 環境
* ブラウザで試しました。
  * Speech Recognition API。ただし、Chromeだけ(他のブラウザは不完全)
    * オンラインじゃないと動作しない ⇒ サーバに処理を丸投げしてるようです。

---
# ためしたこと
+ 話した内容を文字列に変換できるか？
  + (結果)長くてもちゃんとした文章なら、ちゃんと変換してくれました。文脈から正しい単語に変換するようです。 
  + https://kochi0603.github.io/mishima16/Speech2Text.html

+ 何かの決め言葉をトリガーにして、アクションさせられる？
  + (結果)実在しない言葉はうまく変換できないので、決め言葉しだいでうまくいきそうです。
  + https://kochi0603.github.io/mishima16/Speech2Action.html

+ おまけ
  + (結果)呪文を唱える
  + https://kochi0603.github.io/mishima16/Speech2Mol.html

---
## 参考にしたサイト
 * Webページでブラウザの音声認識機能を使おう - Web Speech API Speech Recognition
   * https://qiita.com/hmmrjn/items/4b77a86030ed0071f548

 * SpeechRecognition( MDN )
   * https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition
