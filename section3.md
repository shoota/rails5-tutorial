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
