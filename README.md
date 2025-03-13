# PayCalculator
## 機能

飲み会の幹事さん向けのWebサービスです。
会計する時の計算が楽になる2つの機能を提供します。

- 割り勘計算機能（PAY SPLIT）: 会計に必要な総額（Coins）と人数（People）を入力すると、一人当たりの支払い金額が計算されます。
- 集金計算機能（PAY TOTAL）: 一人当たりの支払い金額（Coins）と人数（People）を入力すると、集金の総額が計算されます。

## 開発
### 前提条件

- Node.js (22.12.0 or newer)
npmコマンドとは：JavaScriptのライブラリやツールを簡単にインストール&管理できる。

### Install

必要なパッケージをインストール。

```:console
npm install
```

### 開発モードを開始

watch コマンドを呼び出す。
下記のstartコマンドと違い、ファイルに変更点があった場合自動でサーバーを再起動。

```:console
npm run watch
```

and access to `http://localhost:8000`

### 通常モードで起動

サイト使用のため、一度のみサーバーを起動。

```:console
npm start
```

and access to `http://localhost:8000`

## 使用技術
### メイン言語
Node.js / TypeScript
### package管理
npm
### Webフレームワーク
Express
### templateエンジン
EJS
### テスト
Jest
Puppeteer
### コード整形
ESLint
Prettier

## ファイル構成

PayCalculator/
├── __tests__/     # プロジェクトのテストファイル。各ページや機能を自動テスト。
├── public/     # CSSファイルや画像ファイル等の静的なファイル置き場。
├── README.md     # このファイル（プロジェクトの説明）
├── package.json # Node.js プロジェクトの設定ファイル
└── src/　　# プロジェクトのメインフォルダ。主にこのフォルダに実装。
    └──　app.ts # アプリケーションのセットアップやサーバーを起動するファイル。ミドルウェアやroutes/で定義されたルーターを読み込む。
    └── routes/　# HTTPリクエストを処理。viewsと連携してリクエストからページ表示までを実行。
         └── home.ts
         └── pay_split.ts # 割り勘計算機能のルーティング処理。
         └── pay_total.ts # 集金計算機能のルーティング処理。
    └── views/ # UIを管理するフォルダ。
    　　　└── layout.ejs　# headerなどの全ページ共通のUI。
         └── home 
              └── top.ejs # top画面
         └── pay_split
              └── index.ejs # 割り勘計算ページ（入力）
              └── result.ejs # 割り勘計算ページ（結果）
         └── pay_total
              └── index.ejs # 集金計算ページ（入力）
              └── result.ejs # 集金計算ページ（結果）

