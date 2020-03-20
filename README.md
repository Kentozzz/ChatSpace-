## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name |string|null: false|

### Association
- has_many :messages
- has_many :groups_users
- has_many :groups,through::groups_users

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user  |reference|null: false, foreign_key: true|
|group |reference|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name  |string|null: false|


### Association
- has_many :messages
- has_many :groups_users
- has_many :users,through::groups_users

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|content|text|      |
|image |string|　　　|
|group_id|integer|null: false, foreign_key: true|
|user_id |integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group- validates :message, precence: true
