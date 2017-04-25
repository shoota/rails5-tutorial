# 2.1 アプリケーションの計画

## 要点

- `scaffold`とRESTを学ぶ
- `rails new`してGemfile書き換え

:heavy_check_mark:　[commit](https://github.com/shoota/toy_app)


- DBテーブルを考える
  - `users`テーブル
    - name :string
    - email :string
  - `microposts`テーブル
    - content :text
    - user_id
  - `user has many microposts`の関係


# 2.2 Usersリソース

## 要点

- `rails generate scaffold`を使ってUserモデルを作る
- `rails g scaffold <モデル単数> [<name>:<type>...]`
- `rails db:migragte`
  - rails5から`rake`は`rails`に変わりました。
- RESTとURL、HTTPメソッドの話。割愛。
- scaffoldで`config/routes.rb`にresourceが追加されていることを確認。
- controllerで宣言した変数`@users`はviewに渡される。(endのあとで)
- GETのメソッドではテンプレートを指定していない。メソッド名(REST)がそのまま名前として解決されている。

:-1: :-1: :-1: :-1: :-1: :-1: :-1: 
 
 実際にやると、`/users`にアクセスしたときに`ArgumentError: key must be 32 bytes`というエラーがでる。
 rails 5.0.0.1とruby 2.4.x系が噛み合わないらしい。
 Gemfileのrailsバージョンを`rails 5.0.1`に変更して解決。今後は`5.0.1`ですすめる。


# 2.3 Micropostsリソース

## 要点

- validation
  - modelに記載する `validates :<name>, validate_method{args: value}`
  - 最大桁数 -> length{maximum: xxx}
  - 必須入力 -> presence: true
- relation (関係の記述で単数形、複数形に注目)
  - `users.rb` -> `has_many :microposts`
  - `microposts.rb` -> `belongs_to :user`
- rails console　（irbです）
- heroku deploy
  - `git push heroku`
  - `heroku run rails db:migrate`
 
 
 #### こんな感じのDB作成ログがでる
 
 ```
$ heroku run rails db:migrate
Running rails db:migrate on ⬢ blooming-gorge-66512... up, run.5522 (Free)
D, [2017-04-25T13:40:33.923961 #4] DEBUG -- :    (48.5ms)  CREATE TABLE "schema_migrations" ("version" character varying PRIMARY KEY)
D, [2017-04-25T13:40:33.941159 #4] DEBUG -- :    (12.7ms)  CREATE TABLE "ar_internal_metadata" ("key" character varying PRIMARY KEY, "value" character varying, "created_at" timestamp NOT NULL, "updated_at" timestamp NOT NULL)
D, [2017-04-25T13:40:33.942719 #4] DEBUG -- :    (0.6ms)  SELECT pg_try_advisory_lock(3490353328371703395);
D, [2017-04-25T13:40:33.956032 #4] DEBUG -- :   ActiveRecord::SchemaMigration Load (0.8ms)  SELECT "schema_migrations".* FROM "schema_migrations"
I, [2017-04-25T13:40:33.971717 #4]  INFO -- : Migrating to CreateUsers (20170419135859)
D, [2017-04-25T13:40:33.973971 #4] DEBUG -- :    (0.5ms)  BEGIN
== 20170419135859 CreateUsers: migrating ======================================
-- create_table(:users)
D, [2017-04-25T13:40:33.987051 #4] DEBUG -- :    (11.9ms)  CREATE TABLE "users" ("id" serial primary key, "name" character varying, "email" character varying, "created_at" timestamp NOT NULL, "updated_at" timestamp NOT NULL)
   -> 0.0130s
== 20170419135859 CreateUsers: migrated (0.
 ```
