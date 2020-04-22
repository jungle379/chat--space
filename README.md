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
|image|string||
|text|text|null: false, foreign_key: true|


### Association
- belongs_to :group
- belongs_to :user
- belongs_to :image


* ## usersテーブル

|Column|Type|Options|
|------|----|-------|
|group|references|null: false, foreign_key: true|

### Association
- has_many :groups, through: :groups_users

* ## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|message|references|null: false, foreign_key: true|


### Association
- belongs_to :user
- belongs_to :message
