# テーブル設計

## usersテーブル

|Column     |Type   |Option       |
|-----------|-------|-------------|
|email      |string |null: false  |
|password   |string |null: false  |
|name       |string |null: false  |
|profile    |text   |null: false  |
|occupation |text   |null: false  |
|position   |text   |null: false  |

### Association

- has_many :prototypes
- hse_many :comments

## prototypesテーブル

|Column     |Type        |Option             |
|-----------|------------|-------------------|
|title      |string      |null: false        |
|catch_copy |text        |null: false        |
|concept    |text        |null: false        |
|image      |ActiveStorageで実装              |
|user       |references  |foreign_key: true  |

### Association

- belongs_to :user
- hse_many   :comments

## commentsテーブル

|Column     |Type        |Option             |
|-----------|------------|-------------------|
|text       |string      |null: false        |
|user       |references  |foreign_key: true  |
|prototype  |references  |foreign_key: true  |

### Association

- belongs_to :user
- belongs_to :prototype