##### [Mishima.syk #16](https://connpass.com/event/164605/)
# 「在宅⇒ヘッドセット⇒音声認識　@tkochi0603」
## 在宅勤務が多くなり、ヘッドセットを付ける機会が増えました。音声認識してみたくなりますよね♪

#### 「Speech Recognition API」でググると結構出てきます。

#### 先に所感ですが、
##### ちゃんとした文章を読むと、ちゃんと変換してくれます。
##### 事前に決めた予約語を認識したら、ある処理を実行する。といったこともできますね。
##### Chromeのみ動作確認しました。Zoomだとマイクのデバイスを確認しないといけませんね(未確認)。

---
# 実装サンプルページ
https://kochi0603.github.io/mishima16/SpeechRecognition.html
### ChromeとEdgeが対応、Firefoxは設定で対応
 Chrome自体が音声認識しているわけではないようです(ネットワークを切断すると動作しない)。
 結構長い文章でも認識してくれる


---
## 参考にしたサイト
### Webページでブラウザの音声認識機能を使おう - Web Speech API Speech Recognition
### https://qiita.com/hmmrjn/items/4b77a86030ed0071f548

### SpeechRecognition( MDN )
### https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition
