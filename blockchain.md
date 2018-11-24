# ブロックチェーンアプリケーションのJavaScriptの開発

[資料](https://docs.google.com/presentation/d/1EmXHYEZr4KHixWg_4ttK5r5EeFnOez8Cj2AQ_Sfc6mo/edit)

## QuestというDappsを使った

### Questの説明
コミュニィの成長を促すためのイベントプラットフォーム  

**使い方**
* ホストがトークルームを作成してETHをデポジットする
* Dappsと既存のWebサービスのハイブリット

使っている言語など  
gcp  
kubernetes   
nginx   
react 
golang  
mysql  
node.js  
socket.io  

**フロントエンドライブラリ**  
React create react app  
react router　　
redux  
typescript  
socket.io  

Typescriptの型チェックが優秀だった  







### Dappsの説明
**非中央集権の分散型アプリケーション**  
中央管理者が存在せずオペレーションが自動

**ブロックチェーンのjsライブラリ  
Truffle**  
コントラクトのコンパイルやデプロイ、テストが出来る


#### DAppsを利用するのに課題・解決
* Walletが必要なので敷居が高い  
→Wallet付きのアプリにする
* トランザクション処理を待つ間のUXを考える余地がある 　
→ローディングの工夫
* Dapps用のライブラリが少ない  
→DAppsのフロントエンドエンジニアが少ないのでがんばるしかない

**Solidityという言語を使ってDAppsを作れる**

## 開発で使ったフロントエンドライブラリの話

### readct,Redux
