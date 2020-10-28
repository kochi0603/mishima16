##### [Mishima.syk #16](https://connpass.com/event/164605/)　2020/11/28
# 「気軽に音声認識　@tkochi0603」
* 在宅勤務でWeb会議が多くなり、ヘッドセットを付ける機会が増えました。
* 音声認識を使って業務を効率化できませんかね？

---
# 環境
* 気軽に音声認識を試す環境
  * Browserで試したい。アプリは使わない。
    * Speech Recognition API。ただし、Chromeだけ(他のブラウザは不完全)
    * オンラインじゃないと動作しない ⇒ サーバに処理を丸投げしてるようです。

---
# ためしたこと
+ 話した内容を文字列に変換できるか？
  + (結果)長くてもちゃんとした文章なら、ちゃんと変換してくれました。文脈から正しい単語に変換するようです。 
+ 何かの決め言葉をトリガーにして、アクションさせられる？
  + (結果)実在しない言葉はうまく変換できないので、決め言葉しだいでうまくいきそうです。

---
# 実装サンプルページ
https://kochi0603.github.io/mishima16/SpeechRecognition.html

---
## 参考にしたサイト
 * Webページでブラウザの音声認識機能を使おう - Web Speech API Speech Recognition
  * https://qiita.com/hmmrjn/items/4b77a86030ed0071f548

 * SpeechRecognition( MDN )
  * https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition
