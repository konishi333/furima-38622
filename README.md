# テーブル設計

## users テーブル ： ユーザー管理テーブル

| Column             | Type    | Options                   |
| ------------------ | ------- | ------------------------- |
| nickname           | string  | null: false               |
| email              | string  | null: false, unique: true |
| encrypted_password | string  | null: false               |
| first_name         | string  | null: false               |
| last_name          | string  | null: false               |
| first_name_kana    | string  | null: false               |
| last_name_kana     | string  | null: false               |
| birthday           | date    | null: false               |


##  itemsテーブル ： 商品出品テーブル

| Column            | Type       | Options                        |
| --------------    | ---------- | ------------------------------ |
| name              | string     | null: false                    |
| description       | text       | null: false                    |
| category_id       | string     | null: false                    |
| status_id         | string     | null: false                    | 
| payment_method_id | integer    | null: false                    |
| shipping_area_id  | integer    | null: false                    |
| shipping_day_id   | integer    | null: false                    |
| selling_price     | integer    | null: false                    |
| user              | references | null: false, foreign_key: true |

## historiesテーブル ： 商品履歴テーブル

| Column        | Type       | Options                        |
| ------------- | ---------- | ------------------------------ |
| user          | references | null: false, foreign_key: true |
| item          | references | null: false, foreign_key: true |


## deliveriesテーブル ： 配送先情報テーブル
| Column         | Type    | Options     |
| -------------- | ------- | ----------- |
| phone_number   | string  | null: false |
| post_code      | string  | null: false |
| prefecture     | integer | null: false |
| municipality   | string  | null: false |
| house_number   | string  | null: false |
| building_name  | string  |             |
| history        | references | null: false, foreign_key: true |

