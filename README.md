# LAMP環境構築課題

## １．使用するOSやサーバ環境について
- OS：　Ubuntu　24.04.3 LTS ←　※課題２でバージョンが変わります
- 構築方法：　VirtualBox
- 参考資料：  
・Ubuntu公式ドキュメント（一次情報）  
・AI（CHATGPT、Jemini）： コマンドの意味や初学者向けの視点の解説に使用  
・Qiita： 環境構築の全体像を把握するための参考
- Ubuntu選定理由  
　自分が普段使用しているOS（Windows）以外に手を出すのは初めてだった為、初学者でも分かりやすいかつ、情報源の多い印象を受けたUbuntuを選択。  
　参考にしたwebサイト (https://qiita.com/free-honda/items/c8776286886b3ea31825)

## ２．OSのインストール


‐ Ubuntuのダウンロード、インストールを実施  
参考にしたwebサイトでは日本語対応版を使用していた為、同じく日本語対応版を使用  
課題１で記載したUbuntuとは異なるverのubuntu-ja-22.04 LTSを以後使用  
参考にしたwebサイト(https://webdesign-programming.com/virtualbox-ubuntu-install/)

☆次回やってみたいこと  
・今回は初学者向けにUbuntuを使用したが、CentOSにしたらどう変わるのかが気になる  
・今回使用したVirtualBox以外の選択肢としてWSL(Windows Subsystem for Linux)も使ってみたい

##  ３．OSインストール後
- サーバのタイムゾーンをJSTにする  

- ファイアウォールの有効化  

- SELinuxを無効


---

<div align="center">

📄 詳しい手順はこちら  
[➡ 課題３ 詳細を見る](課題３.md)

</div>

---  

## ４．Apacheのインストールとwebページが表示される環境作り  
- Apacheのバージョンは2.4系  
- 自動起動するように設定  
- サーバが再起動しても自動で起動するように設定
- VirtualHostの機能を利用し下記要件を満たす
  ・ Webブラウザで`http://<自分の名字>-hbtask.local/` にアクセスすると「こんにちは。ありがとう。」と表示される
  ・ Webブラウザで`http://<自分の名前>-hbtask.local/` にアクセスすると「ありがとう。こんにちは。」と表示される

---

<div align="center">

📄 詳しい手順はこちら  
[➡ 課題４ 詳細を見る](課題４.md)

</div>

---  
