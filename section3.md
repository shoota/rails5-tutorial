# 3.1 セットアップ

## 要点

２章まででやってきたことのおさらい。アプリを新しくつくり、Gemを指定し、githubとherokuにpushする。

:heavy_check_mark:　[repository](https://github.com/shoota/rails5-tutorial-sample_app)


# 3.2 静的ページ

## 要点

- Controllerを作って静的なページを返す
  - `$ rails generate controller StaticPages home help`

> StaticPagesコントローラは一般的なRESTアクションに対応していないことに注意してください。 これは、静的なページの集合に対しては、適切なアクションと言えます。言い換えると、RESTアーキテクチャは、あらゆる問題に対して最適な解決方法であるとは限らないということです。

### railsコマンドでUndo

- `rails generate` <-> `rails destroy`
- `rails db:migrate` <-> `rails rollback`


# 3.3 テストから始める

- http statusをチェックするテストを先にかいて、TDDをやってみる。
  - まずテストを動かしてみる(green)
  - テストを追加(red)
  - `config/route.rb` 
  - `controller#about`
  - `erb` (green)

# 3.4 少しだけ動的なページ

- `assert_select <selector> <expected>`でテストを追加
  - テストを先に書く！！
- `StaitcPages`のerbの共通文字列(title)を`yeild` <-> `provide`でDRYに
- `routes.rb`で`root`を`StaticPagesController::Home`に向ける
  - このテストも書く。（Homeと期待は同じ）

:heavy_check_mark:　[commit](https://github.com/shoota/rails5-tutorial-sample_app/commit/096c72eea68f91f08e2c404037e61c5b14a734cd)

# 3.5 最後に

- `git push`
- `git push heroku`

## 3章のまとめ(3.6は追加のセクション)

- `rails new`、gemインストール、git remote、production環境作成までやった
- controllerだけ`rails g`した
- erbをつかった
- TDDをやった
- DRYにしてみた




- `rails generate` <-> `rails destroy`。
- `rails generate` <-> `rails destroy`
