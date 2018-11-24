# Angular Universal on GoogleAppEngine

@kimamula

TypeScriptを愛している

[資料](https://speakerdeck.com/kimamula/angular-universal-on-google-app-engine)

## What is Angular Universal

AngularでSSRを可能にするためのプロジェクト

* SEOが有利

* パフォーマンスが良い


## How to Agnular Universal


### Get in Start

#### Qick Start
```
ng new project
nd project
ng add @nguniversal/express-engine --clientProject project

npm run build:ssr && npm run server:ssr
```

Qick Startだけではないので
公式ドキュメントを読んだほうがよい

[https://angular.io/guide/universal](https://angular.io/guide/universal)

なぜか
こっちのスターターキットのほうが新しいしお勧め(たぶんドキュメントが古い)
[https://github.com/angular/universal-starter](https://github.com/angular/universal-starter)

* 最小構成
* PreRendering
* ドキュメントより最新


### サーバとクライアントでコードが共通になることに注意する

* サーバとクライアントどちらかでしか動かしたくない処理を適切に制御する

isPlatformBrowserやisPlatformServerで分ける（泥臭い）

* サーバで実行済みの処理がクライアントで重複して実行されないようにする  

Transferstateを使う  
サーバサイドで初期化した状態をクライアントに渡す仕組み(これ便利)  
→サーバサイドのmakeStateKeyでデータを格納しクライアントサイドでgetする


### はまったところ困ったところ  

#### style.cssのSSR
* コンポーネントごとのCSSはSSRされる
* グローバルなSSRはSSRされない  

→適用までに時間がかかる

**解決策**
```  
cssのみをインポートするコンポーネントを作り  
AppServerModuleのbootstrapで指定する
```

#### watchモードで開発したい
公式手順はng serveは用意されていない(いちいちビルドする)  

現状解決策なし


#### Prerender or SSR
ビルド時にhtmlを作成する方法がPrerender  

動的なページには不向きだがサーバサイドとクライアントに負荷がかからない

動的なページにも対応したい（課題）





## Hack Angular Universal
