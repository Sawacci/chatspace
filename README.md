## message table

|Column|Type|Options|
|------|----|-------|
|body|text|-------|
|image|string|-------|
|user_id |integer|null: false, foreign_key: true|
|chatgroup_id|interger|null: false|

### Association
- belongs_to :group
- belongs_to :user

## user table
|Column|Type|Options|
|------|----|-------|
|name|string|null :false|
|email|srting|null :false|
|password|string|null :false|

### Association
- has many :messages
- has many :groups

## group table
|Column|Type|Options|
|------|----|-------|
|name|string|null :false|

### Association
- has many :users
- has many messages

## group_user table
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|


### Association
- has many :groups, though: group_users
- has many :group_users



# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
