# README

## usersテーブル

|   Column   |  Type  |  options    |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

_ has_many :comments
_ has_many :prototypes


## commentsテーブル

|  Column   |  Type      |  options    |
| --------- | ---------- | ----------- |
| text      | text       | null: false |
| user      | references |             |
| prototype | references |             |

### Association

_belongs_to :users
_belongs_to :prototypes


## prototypesテーブル

|   Column   |  Type      |  options                      |
| ---------- | ---------- | ----------------------------- |
| title      | string     | null: false                   |
| catch_copy | text       | null: false                   |
| concept    | text       | null: false                   |
| image      |            | implementation: ActiveStorage |
| user       | references |                               |

### Association

_has_many :comments
_belongs_to :users
