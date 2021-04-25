# テーブル設計

## users テーブル

| Column           | Type   | Options     |
| --------         | ------ | ----------- |
| email            | string | null: false |
|encrypted_password| string | null: false |
| first_name       | string | null: false |
| last_name        | string | null: false |
| birthday         | string | null: false |

### Association
- has_many :products
- has_many :buy_records
- has_many :address



## products テーブル

| Column          | Type        | Options     |
| -------------   | ------------| ----------- |
| products_name   | string      | null: false |
| image           |ActiveStorage| null: false |
| user            |references   | null: false |
| category        | string      | null: false |
| prefecture      | string      | null: false |
| price           | string      | null: false |

### Association
- belongs_to :users
- has_many   :buy_records


## buy_records テーブル

| Column          | Type       | Options     |
| --------------- | ---------- | ------------|
| comment_text    | text       | null: false |
| user            | references | null: false |
| products        | references | null: false |

### Association
- belongs_to :users
- belongs_to :products



## address テーブル

| Column          | Type       | Options     |
| --------------- | ---------- | ------------|
| address         | text       | null: false |
| user            | references | null: false | 
| post_number     | string     | null: false |
| prefecture      | string     | null: false |

### Association
- belongs_to :users