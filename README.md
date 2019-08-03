# README

### DB設計図

## group_users

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
belongs_to :group
belongs_to :user

## groups
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, default:|
### Association
- has_many :messages, through
- has_many :user, through

## messages
|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string||
|user_id|integer|null: false, foreign_key: true, index: true|
|group_id|integer|null: false, foreign_key: true, index: true|
### Association
- belongs_to :user
- has_many :messages


## users
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, default: |
|email|string|null: false, default: |


### Association
 has_many  :messages
 add_index :users, :name,     unique: true
 add_index :users, :email,    unique: true
 

