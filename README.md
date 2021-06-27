# テーブル設計

## usersテーブル

| column     | type   | options  | 
| ---------- | ------ | -------- | 
| email      | string | NOT NULL | 
| password   | string | NOT NULL | 
| name       | string | NOT NULL | 
| profile    | text   | NOT NULL | 
| occupation | text   | NOT NULL | 
| position   | text   | NOT NULL | 

- has_many :comments
- has_many :prototypes

## commentsテーブル

| column    | type       | options  | 
| --------- | ---------- | -------- | 
| text      | text       | NOT NULL | 
| user      | references |          | 
| prototype | references |          | 

- belongs_to :user
- belongs_to :prototypes


## prototypesテーブル

| column     | type       | options  | 
| ---------- | ---------- | -------- | 
| title      | string     | NOT NULL | 
| catch_copy | text       | NOT NULL | 
| concept    | text       | NOT NULL | 
| image      |            |          | 
| user       | references |          | 

- belongs_to :user
- has_many :comments