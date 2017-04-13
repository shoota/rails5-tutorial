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
  - `sqlite3`を`:development :test`のみに移動
- `bundle install`したときに`bundle update`してね、ってエラーになることもあります

bundle update促された


```
Bundler could not find compatible versions for gem "railties":
  In snapshot (Gemfile.lock):
    railties (= 5.0.2)

  In Gemfile:
    coffee-rails (= 4.2.1) was resolved to 4.2.1, which depends on
      railties (< 5.2.x, >= 4.0.0)

    jquery-rails (= 4.1.1) was resolved to 4.1.1, which depends on
      railties (>= 4.2.0)

    rails (= 5.0.0.1) was resolved to 5.0.0.1, which depends on
      railties (= 5.0.0.1)

    sass-rails (= 5.0.6) was resolved to 5.0.6, which depends on
      railties (< 6, >= 4.0.0)

    web-console (= 3.1.1) was resolved to 3.1.1, which depends on
      railties (>= 4.2)

Running `bundle update` will rebuild your snapshot from scratch, using only
the gems in your Gemfile, which may resolve the conflict.

```
