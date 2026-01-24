# -# LAMP環境構築課題

## １．使用するOSやサーバ環境について
- OS：　Ubuntu　24.04.3 LTS
- 構築方法：　VirtualBox
- 参考資料：　公式ドキュメント、AI（CHATGPT、Jemini）
- Ubuntu選定理由  
　自分が普段使用しているOS（Windows）以外に手を出すのは初めてだった為、初学者でも分かりやすいかつ、情報源の多い印象を受けたUbuntuを選択。  
　参考にしたwebサイト (https://qiita.com/free-honda/items/c8776286886b3ea31825)

## ２．OSのインストール


‐ Ubuntuのダウンロード、インストールを実施  
参考にしたwebサイトでは日本語対応版を使用していた為、同じく日本語対応版を使用  
課題１で記載したUbuntuとは異なるverのubuntu-ja-22.04 LTSを以後使用  
参考にしたwebサイト(https://webdesign-programming.com/virtualbox-ubuntu-install/)

##  ３．OSインストール後
- サーバのタイムゾーンをJSTにする  
すでにJSTでしたが確認の為以下のコードを入力  
- timedatectl
- timedatectl set-timezone Asia/Tokyo
- timedatectl status  
<img src="image/image.png" width="400">  
参考にしたwebサイト(https://notes.nakurei.com/post/set-ubuntu-server-timezone-to-jst/)
