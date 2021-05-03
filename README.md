# テーブル設計

## users テーブル

| Column           | Type   | Options     |
| --------         | ------ | ----------- |
| email            | string | null: false, unique: true|
|encrypted_password| string | null: false |
| first_name       | string | null: false |
| last_name        | string | null: false |
| first_name_kana  | string | null: false |
| last_name_kana   | string | null: false |
| nickname         | string | null: false |
| birthday         | string | null: false |

### Association
- has_many :products
- has_many :buy_records




## products テーブル

| Column          | Type        | Options     |
| -------------   | ------------| ----------- |
| products_name   | string      | null: false |
| user            |references   | null: false |
| category_id     | integer     | null: false |
| condition_id    | integer     | null: false |
| payer_id        | integer     | null: false |
| prefecture_id   | integer     | null: false |
| day_id          | integer     | null: false |
| price           | integer     | null: false |
| products_detail | text        | null: false |

### Association
- belongs_to :users
- has_one   :buy_records


## buy_records テーブル

| Column          | Type       | Options                       |
| --------------- | ---------- | ------------                  |
| user            | references | null: false, foreign_key: true|
| products        | references | null: false, foreign_key: true|

### Association
- belongs_to :users
- belongs_to :products
- has_one    :addresses



## addresses テーブル

| Column          | Type       | Options     |
| --------------- | ---------- | ------------|
| post_number     | string     | null: false |
| prefecture      | integer    | null: false |
| town            | string     | null: false |
| townnumber      | string     | null: false |
| building        | string     |             |
| phonenumber     | string     | null: false |

### Association
- belongs_to :users
- belongs_to :buy_records