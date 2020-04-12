## usersテーブル

| Column  	| Type    | Options     |
| :-------	| :------ | :---------- |
| name	 	  | string  | null: false, index: true |
| email   	| string  | null: false |
| password  | string  | null: false |
### Association
- has_many :posts
- has_many :groups_users
- has_many :groups, through: :groups_users


## groupsテーブル

| Column  	| Type    | Options     |
| :-------	| :------ | :---------- |
| group_name| string  | null: false |


### Association
- has_many :posts
- has_many :groups_users
- has_many :users, through :groups_users

## groups_usersテーブル

| Column   | Type    | Options                        |
| :------- | :------ | :----------------------------- |
| user_id  | integer | null: false, foreign_key: true |
| group_id | integer | null: false, foreign_key: true |

### Association

- belongs_to :group
- belongs_to :user


## postsテーブル

| Column  	| Type    | Options     |
| :-------	| :------ | :---------- |
| text		| text    | null: false|
| image		| string  | null: false |
| user_id	| integer | null: false, foreign_key: true |
| group_id	| integer | null: false, foreign_key: true |

### Association
- belongs_to :user
- belongs_to :group

