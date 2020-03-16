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
|group_id|integer|null: false, foreign_key: true|


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
