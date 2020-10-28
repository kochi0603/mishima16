##### [Mishima.syk #16](https://connpass.com/event/164605/)　2020/11/28
# 「気軽に音声認識　@tkochi0603」
* 在宅勤務でWeb会議が多くなり、ヘッドセットを付ける機会が増えました。音声認識してみたくなりますよね♪
* 音声認識を使って業務を効率化できませんかね？
  * 「Speech Recognition API」でググると結構出てきます。

# ためすこと
+ 話した内容を文章にする
  + 長くてもちゃんとした文章なら、ちゃんと変換してくれます
+ 何かの決め言葉を、アクションのトリガーにする
  + 決め言葉しだいです

---
# 実装サンプルページ
https://kochi0603.github.io/mishima16/SpeechRecognition.html
* ChromeとEdgeが対応、Firefoxは設定で対応
 * Chrome自体が音声認識しているわけではないようです(ネットワークを切断すると動作しない)。
 * 長くても、ちゃんとした文章なら、ちゃんと変換してくれます。
 * Zoomのマイクのデバイスを確認しないといけませんね(未確認)。
 * 「事前に決めた予約語を認識したらある処理を実行する」といったこともできますね。

---
## 参考にしたサイト
 * Webページでブラウザの音声認識機能を使おう - Web Speech API Speech Recognition
  * https://qiita.com/hmmrjn/items/4b77a86030ed0071f548

 * SpeechRecognition( MDN )
  * https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition
