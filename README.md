# 設計

## usersテーブル

| Colum             | Type   | Options     |
| -----------       | ------ | ----------- |
| email             | string | null: false ,ユニーク制約 |
| encrypted_password| string | null: false |
| name              | string | null: false |
| profile           | text   | null: false |
| occupation        | text   | null: false |
| position          | text   | null: false |

- has_many :comment
- has_many :prototypes


## commentsテーブル

| Colum             | Type      | Options     |
| -----------       | ------    | ----------- |
| content           | text      | null: false |
| prototype         | reference | null: false, 外部キー|
| user              | reference | null: false, 外部キー|

- belongs_to :user
- belongs_to :prototype


## prototypesテーブル

| Colum             | Type      | Options     |
| -----------       | ------    | ----------- |
| title             | string    | null: false |
| catch_copy        | text      | null: false |
| concept           | text      | null: false |
| user              | reference | null: false, 外部キー|

- belongs_to :user
- has_many :comments