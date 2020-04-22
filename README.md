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
|text|text|null: false, foreign_key: true|


### Association
- belongs_to :group
- belongs_to :user


* ## usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_name|references|null: false, foreign_key: true|

### Association
- has_many :groups, through: :groups_users
- belongs_to :message
- belongs_to :groups_users


* ## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|group_name|references|null: false, foreign_key: true|


### Association
- belongs_to :group_name
