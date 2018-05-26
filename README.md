# ChatSpace
複数人でチャットできるアプリケーション。  
文章や画像を友人とグループ内でやりとりできる。
  

### verson
$ ruby -v ruby 2.4.4p296 (2018-03-28 revision 63013) [x86_64-darwin15]  
$ rails -v Rails 5.1.6  
$ mysql version 5.6.36  
  

## messages table
|Column|Type|Options|
|------|----|-------|
|body|text| |
|image|string|default: ''|
|user_id |integer|null: false, foreign_key: true|
|chat_group_id|integer|null: false|
  

### Association
- belongs_to :chat_group
- belongs_to :user
  

## users table
|Column|Type|Options|
|------|----|-------|
|nickname|string|null :false, unique: true|
|email|srting|null :false|
|password|string|null :false|
  

### Association
- has many :messages
- has many :groups
  

## chat_groups table
|Column|Type|Options|
|------|----|-------|
|name|string|null :false, unique: true|
  

### Association
- has many :users
- has many messages
  

## chat_group_users table
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|chat_group_id|integer|null: false, foreign_key: true|
  

### Association
- has many :chat_groups, though: chat_group_users
- has many :chat_group_users
  
