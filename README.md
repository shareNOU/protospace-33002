#　テーブル設計

## usersテーブル

| Column     | Type   | Options  |
| ---------- | ------ | -------- |
| email      | string | NOT NULL |
| password   | string | NOT NULL |
| name       | string | NOT NULL |
| profile    | text   | NOT NULL |
| occupation | text   | NOT NULL |
| position   | text   | NOT NULL |

### Association

- belongs_to :prototypes
- belongs_to :comments

## prototypesテーブル

| Column     | Type          | Options  |
| ---------- | ------------- | -------- |
| title      | string        | NOT NULL |
| catch_copy | text          | NOT NULL |
| concept    | text          | NOT NULL |
| user       | references    |          |

### Association

- belongs_to :users
- belongs_to :comments

## commentsテーブル

| Column    | Type       | Options  |
| --------- | ---------- | -------- |
| text      | text       | NOT NULL |
| user      | references |          |
| prototype | references |          |

### Association

- belongs_to :users
- belongs_to :prototypes