# テーブル設計

## users テーブル

| Column             | Type   | Options                                   |
| ------------------ | ------ | ------------------------------------------|
| name               | string | null: false                               |
| email              | string | null: false,UNIQUE_key: true              |
| encrypted_password | string | null: false                               |
| profile            |  text  | null: false                               |
| occupation         |  text  | null: false                               |
| position           |  text  | null: false                               |

- has_many :commentsテーブル
- has_many :prototypesテーブル



## comments テーブル

| Column    | Type       | Options                        |
| ----------|------------|--------------------------------|
| content   | text       | null: false                    |
| prototype | references | null: false, foreign_key: true |
|  user     | references | null: false, foreign_key: true |
 
- belongs_to :userテーブル
- belongs_to :prototypeテーブル


## prototypes テーブル

| Column       | Type       | Options                        |
| -------------| ---------- | ------------------------------ |
| title        | string     | null: false                    |
| catch_copy   | text       | null: false                    |
| concept      | text       | null: false,                   |
| user         | references | null: false, foreign_key: true | 

- belongs_to :userテーブル
- has_many :commentsテーブル