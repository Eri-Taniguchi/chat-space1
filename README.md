## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|

### Association
- has_many :groups_users
- has_many :group, through: :groups_users
- has_many :massage


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|title|text|null: false|

### Association
- has_many :groups_users
- has_many :user, through: :groups_users
- has_many :massage


## massagesテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|foreign_key:true|
|group_id|integer|foreign_key:true|
|body|text|null: false|
|image|string|null:false|

### Association
- belongs_to :user
- belongs_to :group