# 1.1 はじめに

## 要点

- ドキュメントの読み方、前提知識などの説明。Web開発経験あれば読み飛ばして良い
- HTML/CSS/js/SQLの基本、gitは理解してる前提ですよ
  - わからないときは参考になるサイトをみること

# 1.2 さっそく動かす

## 要点

- 公式では開発環境はCloud9を使用していく
  - Rails　tutorial用のテンプレートプロジェクトが用意されている
  - ___自分はMacに開発環境つくることにする___


# 1.3 最初のアプリケーション

## 要点

- 最初のアプリケーションとして`hello_app`をつくる
  - `rails _5.0.0.1 new hello_app`
- `rails new`すると`bundle install`が自動実行される
- rails tutorial用にgemのバージョンを固定する

___実際のソースは[このリポジトリ](https://github.com/shoota/rails5-tutorial-hello_app)___

### bundler

- ライブラリ（gem）のパッケージマネージャ
- gemのバージョンは`Gemfile`にかいてある
- Gemfileでのバージョン指定の方法に関する説明
- `指定なし`：最新版をとってくる
  - `gem 'rails', '5.0.0.1'`：完全固定
  - `gem 'uglifier', '>= 1.3.0'` ：1.3.0以上
  - `gem 'coffee-rails', '~> 4.0.0'`：4.0.xの最新
- Gemfileを編集して`bundle install`
