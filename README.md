# README

### DB設計図

## group_user

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
belongs_to :group
belongs_to :user

## group
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, default:|
### Association
- belongs_to :group
- belongs_to :user

## messages
|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|null: false, default:|
|user_id|integer|null: false, foreign_key: true, index: true|
|group_id|integer|null: false, foreign_key: true, index: true|
### Association



## users
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, default: |
|email|string|null: false, default: |


### Association
 has_many  :messages
  

