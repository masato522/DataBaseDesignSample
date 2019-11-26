# ChatSpace DB設計

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|

### Association

- has_many :groups
- has_many :comments
- has_many :images
- has_many :groups-users
- has_many :groups, through: :groups-users

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|title|string|null: false|
|user-id|string|null: false|

### Association

- belongs_to :user
- has_many :comments
- has_many :images
- has_many :groups_users
- has_many :users, through: :groups-users


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
