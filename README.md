# my_rails7_2_starter

```

* Ruby 3.3.6
* Rails 7.2.1
* Node.js v20.18.0
* esbuild (JavaScriptバンドラー)
* Tailwind (CSSフレームワーク)
* PostgreSQL (データベース)
* 開発環境の構築 Docker・docker compose

```

上記の構成の初期セットアップ済みテンプレート** です。
`rails new` からの環境構築を省略して、**テンプレートからすぐ新規アプリを作成できる**ことを目的としています。


## ✅ 使用方法（Template Repository 前提）

このリポジトリは **Template Repository** として公開されています。
他のユーザーは直接変更できず、**「Use this template」ボタン**から自身のリポジトリを作成して利用してください。


### 1. テンプレートから新しいリポジトリを作成

GitHub の **「Use this template」** ボタンから新しいリポジトリを作成します。
例: `my_app_name`

その後、ローカルに clone します。

```bash
git clone https://github.com/yourname/my_app_name.git
cd my_app_name
```


### 2. 🔐 Rails の credentials（master.key）を新規発行

テンプレートには **`config/master.key` / `config/credentials.yml.enc` は含まれていません**。
新しいアプリとして利用する際は、必ず新規発行してください。

```bash
rm -f config/master.key config/credentials.yml.enc
EDITOR="vim" bin/rails credentials:edit
```

※ Vim の代わりに `code`（VSCode）や `nano` も使用可能です。


### 3. Git の紐付け確認（必要なら初期化）

Template から作ったリポジトリには初期 commit が残っています。
必要に応じてリポジトリ名や origin を変更して管理してください。

```bash
# もしテンプレート元の履歴を残したくない場合
rm -rf .git
git init
git add .
git commit -m "Initial commit from my_rails7_2_starter"
```


## 🚀 Docker でアプリを起動

```bash
docker compose build
docker compose run --rm web yarn install
docker compose up -d
```

ブラウザで以下にアクセスして表示されればセットアップ完了です：

👉 [http://localhost:3000](http://localhost:3000)


## ✅ よくあるカスタマイズ（任意）

| 内容              | 対象ファイル                      |
| --------------- | --------------------------- |
| アプリ名（モジュール名）の変更 | `config/application.rb`     |
| サービス名・DB名の変更    | `docker-compose.yml`        |
| 開発用環境変数の管理      | `.env` / `.env.example` を作成 |


## 🛡 Template Repository の使い方の注意

* このリポジトリは **他ユーザーが直接変更できないよう保護** されています
* main ブランチを保護しているため、push する場合は必ず自身のコピー／テンプレートから作成したリポジトリで行ってください
* 元リポジトリに直接 PR を送ることは想定していません


## 📝 新しいリポジトリとして GitHub に公開する場合

```bash
git remote add origin https://github.com/yourname/my_app_name.git
git push -u origin main
```

✅ 「yourname」や「my_app_name」を自身の GitHub 名／アプリ名に差し替えるのを忘れないでください。


## ライセンス

自由に改変・再利用して構いません。（パブリック／プライベートどちらも可）

## 注意
RUNTEQ の卒業制作でこのリポジトリをそのまま利用することはご遠慮ください。
まだ Rails アプリを自分で作った経験がない方がそのまま使うと、卒業制作としての学習効果が薄れてしまう可能性があります。
ただし、ミニアプリや練習用のプロジェクトなど、学習目的での利用は問題ありません。
