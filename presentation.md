title: How to オンラインランキング
class: animation-fade
layout: true

<!-- This slide will serve as the base layout for all your slides -->
.bottom-bar[
  {{title}}
]

---

class: impact

# {{title}}
## 90分完全マスター講座 for Monaca


.right[<img src="img/takano.png" alt="takano.png" width="150px">]

.footnote[
.left[
.size_small_7[
Copyright 2019 FUJITSU CLOUD TECHNOLOGIES LIMITED<br>
Created by Natsumo Ikeda
]
]
]

---
title: はじめに
layout: true
class: center, middle, animation-fade

---
# {{title}}

---
title: はじめに
layout: false

# 資料

.size_large_18[
__https://natsumo.github.io/MakeOnlineRanking/__
]

### ダウンロード方法
.size_small_7[
* Google Chrome でURLを開く
* 「設定」＞「印刷」＞送信先で「PDFに保存」を選択する
* プレビュー画面で画像が全て読み込まれたことを確認して「保存」をクリック
]

.bottom-bar[
  {{title}}
]

---
title: はじめに

# 取り組むこと
## オンラインランキング機能を実装しましょう

.col-8[
.size_small_9[
.color_pink[__Monaca__] に元々備わっているサンプルプロジェクトである「ブロック崩し」アプリ追加開発してオンラインランキング機能を付加します。オンラインランキング機能部分は１から１０まで全てハンズオンしていただきます。
]
.size_small_7[
* ゼロベースからあっという間にランキング機能を追加できます
* ランキング機能は高速で実装できてしまうことがよくわかります
]
]
.col-4[
.center[<img src="img/ranking.png" alt="ranking.png" width="250px">]
]

.bottom-bar[
  {{title}}
]

---
title: はじめに

# 使うもの
## クラウドアプリ開発環境「Monaca」

.size_small_7[
HTML5 / JavaScript / CSS3 で iOS, Android 両OSのスマートフォンアプリが同時に開発できるクラウド開発環境です。オンラインランキングを実装する開発中のアプリがあればそれに組み込むのが一番！ですが開発中のゲームアプリが特に無く、とりあえず使い勝手を試したいのであればサンプルゲームがあって取り組みやすい __Monaca__ がおすすめです👌
]

.col-6[
.center[<img src="img/about_Monaca.png" alt="about_Monaca.png" width="400px">]
]

.col-6[
.size_small_7[
* .color_pink[__ニフクラ mobile backend__] との連携が圧倒的に楽
* __環境構築不要__ （ブラウザで開発）
* 学びやすい __スクリプト言語__
* しかも __無料__ から使える
]
]

.bottom-bar[
  {{title}}
]

---
title: はじめに

# 使うもの
## クラウドデータベース「ニフクラ mobile backend」

.size_small_7[
ランキングを作成してそれを __オンライン化__ するために必要なのが「 __クラウドデータベース__ 」です。一般にデータベースを自前で１から開発・・・となるとかなり大変ですが、 __構築不要ですぐに使えるクラウドデータベース__ である __ニフクラ mobile backend__ を活用すればあっという間に実装することができます👌
]

.col-6[
.center[<img src="img/about_NCMB.png" alt="about_NCMB.png" width="250px">]
]

.col-6[
.size_small_7[
* .color_pink[__Monaca__] との連携が圧倒的に楽
* __環境構築不要__ （ブラウザから管理できる）
* SDKはなんと５種類
  * .size_small_7[JavaScript/iOS(Swift/objective-C)/Android(Java)/Unity(C#)]
* しかも __無料__ から使える
]
]

.bottom-bar[
  {{title}}
]

---
title: はじめに

# 作るもの
## オンラインランキング機能付きブロック崩し
.col-4[
.size_small_9[
Monaca既存サンプルプロジェクト「ブロック崩し」アプリに追加実装をして、「オンラインランキング機能付きブロック崩し」アプリを作ります。
]
]
.col-8[
.center[<img src="img/game02.png" alt="game02.png" width="650px">]
]
.bottom-bar[
  {{title}}
]


---
title: はじめに

# 作り方・作業手順

.size_small_7[
1. Monacaのアカウントを作成する
1. 「ブロック崩し」プロジェクトを作る
1. ニフクラ mobile backend のアカウントを作成する
1. ニフクラ mobile backend と連携する
  1. ニフクラ mobile backend にアプリを作成する
  1. Monaca に ニフクラ mobile backend のSDKを導入する
  1. SDKを初期化する
1. 機能実装①：ゲームスコアを保存する
1. ①の動作確認
1. 機能実装②：ランキングを取得する
1. ②の動作確認
]

.bottom-bar[
  {{title}}
]

---
title: 1.&nbsp;Monacaのアカウントを作成する
layout: true
class: center, middle, animation-fade

---
# {{title}}

---
title: 1.&nbsp;Monacaのアカウントを作成する
layout: false

.col-8[
.size_small_7[
* Monaca Education を開く
* 「アカウント作成」をクリックする
]
.center[<img src="img/MonacaEducation01.png" alt="MonacaEducation01.png" width="600px">]
__https://edu.monaca.io/__
]
.col-4[
<br><br>
.size_small_7[
✅__既にアカウントをお持ちの方__
* 通常版 Monaca アカウント
* Monaca Education アカウント
]
.size_small_5[
そのままご利用ください。上記どちらでもOKです。<br>
ただし、本資料は Monaca Education アカウントを使った前提で操作説明を記述しています。通常版をご利用の場合は多少操作手順が異なる場合がございます。
]
]
.size_small_7[
✅Monaca利用時、ブラウザは必ず __Google Chrome__ を使用してください
]


.bottom-bar[
  {{title}}
]

---
title: 1.&nbsp;Monacaのアカウントを作成する

.col-6[
.size_small_7[
* 「メールアドレス」と「パスワード」を入力します
* 「アカウント新規作成」をクリックします
]
.center[<img src="img/MonacaEducation02.png" alt="MonacaEducation02.png" width="350px">]
]

.col-6[
.size_small_7[
* 入力した「メールアドレス」に確認メールが発砲されます
]
<br>
.center[<img src="img/MonacaEducation03.png" alt="MonacaEducation03.png" width="450px">]
]
.bottom-bar[
  {{title}}
]

---
title: 1.&nbsp;Monacaのアカウントを作成する

.col-6[
.size_small_7[
* ブラウザの別タブを開き、メールを確認します
* 送メール本文にある「本登録はこちら」をクリックします
]
.center[<img src="img/MonacaEducation04.png" alt="MonacaEducation04.png" width="450px">]
]

.col-6[
.size_small_7[
* 「利用プラン選択」＞「Freeプラン」を選択します
* 「お名前」を入力して「次に進む」をクリックします

]
.center[<img src="img/MonacaEducation05.png" alt="MonacaEducation05.png" width="350px">]
]
.bottom-bar[
  {{title}}
]

---
title: 1.&nbsp;Monacaのアカウントを作成する

.col-6[
.size_small_7[
* 「OK」をクリックします
]
.center[<img src="img/MonacaEducation06.png" alt="MonacaEducation06.png" width="450px">]
]

.col-6[
.size_small_7[
* 「ダッシュボードに進む」をクリックします

]
.center[<img src="img/MonacaEducation07.png" alt="MonacaEducation07.png" width="400px">]
]
.bottom-bar[
  {{title}}
]

---
title: 1.&nbsp;Monacaのアカウントを作成する

.col-5[
.size_small_7[
* 「同意する」をクリックします
]
.center[<img src="img/MonacaEducation08.png" alt="MonacaEducation09.png" width="350px">]
]

.col-7[
.size_small_7[
* ダッシュボードが表示されます
* これでアカウント作成とログインが完了しました

]
.center[<img src="img/MonacaEducation09.png" alt="MonacaEducation09.png" width="500px">]
]

.right_under[
.size_small_7[
✅これでアカウント作成とログインが完了しました
]
]
.bottom-bar[
  {{title}}
]

---
title: 2.&nbsp;「ブロック崩し」プロジェクトを作る
layout: true
class: center, middle, animation-fade

---
# {{title}}

---
title: 2.&nbsp;「ブロック崩し」プロジェクトを作る
layout: false

.col-6[
.size_small_7[
* 「新しいプロジェクトを作る」をクリックします
]
.center[<img src="img/MakePJ01.png" alt="MakePJ01.png" width="400px">]
]

.col-6[
.size_small_7[
* 「テンプレート」＞「ブロック崩し」を選択します

]
.center[<img src="img/MakePJ02.png" alt="MakePJ02.png" width="450px">]
]
.bottom-bar[
  {{title}}
]

---
title: 2.&nbsp;「ブロック崩し」プロジェクトを作る

.col-6[
.size_small_7[
* 「プロジェクトの情報」はそのままで「作成」をクリックします
]
.center[<img src="img/MakePJ03.png" alt="MakePJ03.png" width="400px">]
]

.col-6[
.size_small_7[
* プロジェクトが作成されました

]
.center[<img src="img/MakePJ04.png" alt="MakePJ04.png" width="450px">]
]
.bottom-bar[
  {{title}}
]

---
title: 2.&nbsp;「ブロック崩し」プロジェクトを作る


.size_small_7[
* 作成されたプロジェクトを選択します
* 「クラウドIDEで開く」をクリックします
]
.center[<img src="img/MakePJ05.png" alt="MakePJ05.png" width="850px">]

.bottom-bar[
  {{title}}
]

---
title: 2.&nbsp;「ブロック崩し」プロジェクトを作る


.size_small_7[
* プロジェクトが開かれます
]
.center[<img src="img/MakePJ06.png" alt="MakePJ06.png" width="800px">]

.bottom-bar[
  {{title}}
]

.right_under[
.size_small_7[
✅これでMonaca側の準備は整いました。続いて ニフクラ mobile backend 側の準備をしていきます。
]
]


---
title: 3.&nbsp;ニフクラ mobile backend のアカウントを作成する
layout: true
class: center, middle, animation-fade

---
# {{title}}

---
title: 3.&nbsp;ニフクラ mobile backend のアカウントを作成する
layout: false

.col-8[
.size_small_7[
* ニフクラ mobile backend を開く
* 「無料登録」をクリックする
]
.center[<img src="img/ncmb01.png" alt="ncmb01.png" width="600px">]
__https://mbaas.nifcloud.com/__
]
.col-4[
<br><br>
.size_small_7[
✅__既にアカウントをお持ちの方__
]
.size_small_5[
そのままご利用ください。
]
]

.bottom-bar[
  {{title}}
]




.bottom-bar[
  {{title}}
]

---
title: 3.&nbsp;ニフクラ mobile backend のアカウントを作成する

# ふげふげ



.bottom-bar[
  {{title}}
]

---
title: 4.&nbsp;ニフクラ mobile backend と連携する
layout: true
class: center, middle, animation-fade

---
# {{title}}

---
title: 4.&nbsp;ニフクラ mobile backend と連携する
layout: false

# ホゲホゲ



.bottom-bar[
  {{title}}
]

---
title: 4.&nbsp;ニフクラ mobile backend と連携する

# ふげふげ



.bottom-bar[
  {{title}}
]

---
title: 5.&nbsp;機能実装①：ゲームスコアを保存する
layout: true
class: center, middle, animation-fade

---
# {{title}}

---
title: 5.&nbsp;機能実装①：ゲームスコアを保存する
layout: false

# ホゲホゲ



.bottom-bar[
  {{title}}
]

---
title: 5.&nbsp;機能実装①：ゲームスコアを保存する

# ふげふげ



.bottom-bar[
  {{title}}
]

---
title: 6.&nbsp;①の動作確認
layout: true
class: center, middle, animation-fade

---
# {{title}}

---
title: 6.&nbsp;①の動作確認
layout: false

# ホゲホゲ



.bottom-bar[
  {{title}}
]

---
title: 6.&nbsp;①の動作確認

# ふげふげ



.bottom-bar[
  {{title}}
]

---
title: 7.&nbsp;機能実装②：ランキングを取得する
layout: true
class: center, middle, animation-fade

---
# {{title}}

---
title: 7.&nbsp;機能実装②：ランキングを取得する
layout: false

# ホゲホゲ



.bottom-bar[
  {{title}}
]

---
title: 7.&nbsp;機能実装②：ランキングを取得する

# ふげふげ



.bottom-bar[
  {{title}}
]

---
title: 8.&nbsp;②の動作確認
layout: true
class: center, middle, animation-fade

---
# {{title}}

---
title: 8.&nbsp;②の動作確認
layout: false

# ホゲホゲ



.bottom-bar[
  {{title}}
]

---
title: 8.&nbsp;②の動作確認

# ふげふげ



.bottom-bar[
  {{title}}
]

---
title: おわりに
layout: true
class: center, middle, animation-fade

---
# {{title}}

---
title: おわりに
layout: false

# 補足と課題



.bottom-bar[
  {{title}}
]

---
title: おわりに

# 授業での活用

* 授業でゲームを作らせて機能拡張にクラウドを活用する
* 学習指導要領に明記されたデータベースの活用として（高校）

.bottom-bar[
  {{title}}
]

---
title: おわりに

# 学校様向けご利用プランのご案内

* ライセンス付き参考書を販売しているよというページ

画像とか

* 詳細についてはお問い合わせください

メールアドレスとか

.bottom-bar[
  {{title}}
]

---
title: 本日はご参加いただきありがとうございました！
class: animation-fade
layout: true

---
class: impact

## {{title}}
