## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name |integer|null: false, foreign_key: true|
|email|integer|null: false, foreign_key: true|
|password|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- has_many :groups through: :users_groups
- has_many :messages

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id |integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name  |integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|


### Association
- has_many :message
- has_many :users,through::groups_users

## messageテーブル

|Column|Type|Options|
|------|----|-------|
|body  |text|       |
|image |string   |null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|user_id |integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

### Validation
- validates :message, precence: true
