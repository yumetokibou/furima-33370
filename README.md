# テーブル設計

## users テーブル

| Column           | Type   | Options     |
| --------         | ------ | ----------- |
| email            | string | null: false |
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
- has_many :address



## products テーブル

| Column          | Type        | Options     |
| -------------   | ------------| ----------- |
| products_name   | string      | null: false |
| user            |references   | null: false |
| category        | string      | null: false |
| condition       | string      | null: false |
| payer           | string      | null: false |
| prefecture      | string      | null: false |
| days            | string      | null: false |
| price           | string      | null: false |
| products_detail | text        | null: false |

### Association
- belongs_to :users
- has_many   :buy_records


## buy_records テーブル

| Column          | Type       | Options                       |
| --------------- | ---------- | ------------                  |
| user            | references | null: false, foreign_key: true|
| products        | references | null: false                   |

### Association
- belongs_to :users
- belongs_to :products



## addresses テーブル

| Column          | Type       | Options     |
| --------------- | ---------- | ------------|
| creditnumber    | string     | null: false |
| validity        | string     | null: false | 
| securitycode    | string     | null: false | 
| post_number     | string     | null: false |
| prefecture      | string     | null: false |
| town            | string     | null: false |
| townnumber      | string     | null: false |
| building        | string     | null: false |
| phonenumber     | string     | null: false |

### Association
- belongs_to :users