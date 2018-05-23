### verson
$ ruby -v ruby 2.3.1p112 (2016-04-26 revision 54768) [x86_64-darwin15]
$ rails -v Rails 5.0.7
$ mysql version 5.6.36 

## message table

|Column|Type|Options|
|------|----|-------|
|body|text| |
|image|string| |
|user_id |integer|null: false, foreign_key: true|
|chat_group_id|interger|null: false|

### Association
- belongs_to :chat_group
- belongs_to :user

## user table
|Column|Type|Options|
|------|----|-------|
|nickname|string|null :false, unique: true|
|email|srting|null :false|
|password|string|null :false|

### Association
- has many :messages
- has many :groups

## group table
|Column|Type|Options|
|------|----|-------|
|name|string|null :false, unique: true|

### Association
- has many :users
- has many messages

## group_user table
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|chat_group_id|integer|null: false, foreign_key: true|


### Association
- has many :chat_groups, though: chat_group_users
- has many :chat_group_users

