## users テーブル

| Column             | Type    | Options     |
| ------------------ | ------- | ----------- |
| nickname           | string  | null: false |
| email              | string  | null: false |
| encrypted_password | string  | null: false |

### 画像はActiveStorageを使用

### Association

- has_many :zines
- has_many :posts


## zines テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| user_id | references | null: false, foreign_key: true |
| release | boolean    | default: false, null: false    |
| year    | string     | default: false                 |
| month   | string     | default: false                 |

### Association

- belongs_to :user
- has_many :posts


## posts テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| url     | text       | null: false                    |
| user_id | references | null: false, foreign_key: true |
| zine_id | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :zine