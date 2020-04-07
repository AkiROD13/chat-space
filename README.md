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

# char-space DB設計
## usersテーブル
|Culumn|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|username|string|null: false|
### Association
- has_many :messages
- has_many :groups

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|groupname|string|null :false|
|user_id|intedger|null :false, foreign_key: true|
### Association
- has_many :users
- berongs_to :message

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|text|text||
|image|text||
|postedtime|string|null: false|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :users
- berongs_to :group
