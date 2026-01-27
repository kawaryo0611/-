# LAMP環境構築課題

## １．使用するOSやサーバ環境について
- OS：　Ubuntu　24.04.3 LTS
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
すでにJSTだったが確認の為以下のコードを入力  
-timedatectl  
-timedatectl set-timezone Asia/Tokyo  
-timedatectl status    
<img width="628" height="437" alt="image" src="https://github.com/user-attachments/assets/ce190bda-4261-4329-b983-285b5de546aa" />  

参考にしたwebサイト(https://notes.nakurei.com/post/set-ubuntu-server-timezone-to-jst/)  
man = manual  

- NTPサーバとの時刻同期  
-ntp1.jst.mfeed.ad.jp  
-ntp2.jst.mfeed.ad.jp  
-ntp3.jst.mfeed.ad.jp

<img width="624" height="320" alt="image" src="https://github.com/user-attachments/assets/73ca9c78-5164-46f5-9007-4e133b50c126" />  

それっぽいマニュアルがないか試しに入力したが見つからなかった為ドキュメント探し。

chronyをインストールするコマンドを実行  
sudo apt install chrony  

NTPサーバとの時刻合わせのコマンドを実行  
ntpdate -q ntp1.jst.mfeed.ad.jp  
ntpdate -q ntp2.jst.mfeed.ad.jp  
ntpdate ntp3.jst.mfeed.ad.jp  

ntp1,ntp2は確認だけ行う為にオプションのqを付けたがntp3は除いている  
参考にしたwebサイト(https://zenn.dev/shiragi/articles/92079c2b4613de)

- ファイアウォールの有効化

まずは別サイトや公式ドキュメントは見ず、課題文に記載されている「firewalld」をそのまま入力し実行  
ターミナルからの応答でインストールコマンドが判明、そしてそれを実行  
  sudo apt install firewalld  
  
ダウンロードはしたが、実装方法が分からない為ひとまずman firewalldと入力  
全文目を通したがどの部分を参考にすべきか不明な為、より簡易的な表示を出せるコマンドに変更  
  firewalld --help  
  
コマンドをルート権限にする必要があったので打ち直す  
  sudo firewalld --help  


<img width="724" height="498" alt="image" src="https://github.com/user-attachments/assets/40198f2f-8a2a-4816-b167-8725cda6b958" />

ただ、この情報を見ても私には有効化の方法は分からなかった為、ここで調べることを決める  
公式のWebサイトを参考に、コマンドを入手、実際に入力してみる  
  firewall-cmd --state  
  
結果、「running」と返答があった為有効化されていることを確認  
参考にしたWebサイト(https://firewalld.org/documentation/utilities/firewall-cmd.html)  

余談：CHATGPTで補足情報として、Ubuntuでは通常「ufw」のコマンドが主に使用されると判明  
そこでufwについて少し調べる  
  UFW  Uncomplicated  Firewall  
    Uncomplicated = 打ち消しの意味のun  ＋　複雑の意味のcomplicated　= 簡単  
    
つまり、ファイアウォールを簡単に扱う為のツールらしい  
せっかくUbuntuを今回使っているので、先に知っていればと後悔  
もし実務でまたUbuntuを使用する機会があり、ファイアウォールを導入するタイミングがあれば  
次はufwのコマンドを使って実施する  
参考にしたWebサイト(https://kirakuniit.com/ufw-explanation/)  

せっかく知識を得たのでついでにufwでの有効化と確認だけやってみた  
<img width="609" height="185" alt="image" src="https://github.com/user-attachments/assets/7c311ca7-bf12-481f-9b8d-e39ddc1dfef1" />  

