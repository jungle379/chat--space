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

* ## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

* ## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|
|image|string|
|text|text|


### Association
- belongs_to :group
- belongs_to :user


* ## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|references|null: false|

### Association
- has_many :groups, through: :groups_users
- has_many :messages
- has_many :groups_users


* ## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|references|null: false|


### Association
- has_many :group_users
- has_many :users, through: :group_users
- has_many :messages

