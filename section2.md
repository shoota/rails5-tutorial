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


:-1: :-1: :-1: :-1: :-1: :-1: :-1: 
 
 実際にやると、`/users`にアクセスしたときに`ArgumentError: key must be 32 bytes`というエラーがでる。
 rails 5.0.0.1とruby 2.4.x系が噛み合わないらしい。
 Gemfileのrailsバージョンを`rails 5.0.1`に変更して解決。今後は`5.0.1`ですすめる。
