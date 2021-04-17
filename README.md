# テーブル設計

## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| email    | string | null: false |
|password  | string | null: false |
| name     | string | null: false |




## products テーブル

| Column          | Type        | Options     |
| -------------   | ------------| ----------- |
| products_name   | string      | null: false |
| image           |ActiveStorage| null: false |
| user            |references   | null: false |



## buy_records テーブル

| Column          | Type       | Options     |
| --------------- | ---------- | ------------|
| comment_text    | text       | null: false |
| user            | references | null: false |



## address テーブル

| Column          | Type       | Options     |
| --------------- | ---------- | ------------|
| address         | text       | null: false |
| user            | references | null: false |
