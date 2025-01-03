# Instagram Clone Database

This project is a MySQL database schema for an Instagram clone application. It includes tables for users, photos, comments, likes, follows, tags, and photo tags, allowing for a basic social media experience similar to Instagram.

## Database Structure

The database consists of the following tables:

### 1. Users Table

- **Table Name**: `users`
- **Description**: Stores user information.
- **Columns**:
  - `id`: INT, Primary Key, Auto Increment
  - `username`: VARCHAR(255), Unique
  - `created_at`: TIMESTAMP, Default to current timestamp

### 2. Photos Table

- **Table Name**: `photos`
- **Description**: Stores photos uploaded by users.
- **Columns**:
  - `id`: INT, Primary Key, Auto Increment
  - `image_url`: VARCHAR(255), URL of the photo
  - `user_id`: INT, Foreign Key referencing `users(id)`
  - `created_at`: TIMESTAMP, Default to current timestamp

### 3. Comments Table

- **Table Name**: `comments`
- **Description**: Stores comments made on photos.
- **Columns**:
  - `id`: INT, Primary Key, Auto Increment
  - `comment_text`: VARCHAR(255), Text of the comment
  - `photo_id`: INT, Foreign Key referencing `photos(id)`
  - `user_id`: INT, Foreign Key referencing `users(id)`
  - `created_at`: TIMESTAMP, Default to current timestamp

### 4. Likes Table

- **Table Name**: `likes`
- **Description**: Stores likes on photos by users.
- **Columns**:
  - `user_id`: INT, Foreign Key referencing `users(id)`
  - `photo_id`: INT, Foreign Key referencing `photos(id)`
  - `created_at`: TIMESTAMP, Default to current timestamp
- **Primary Key**: (`user_id`, `photo_id`)

### 5. Follows Table

- **Table Name**: `follows`
- **Description**: Stores follow relationships between users.
- **Columns**:
  - `follower_id`: INT, Foreign Key referencing `users(id)`
  - `followee_id`: INT, Foreign Key referencing `users(id)`
  - `created_at`: TIMESTAMP, Default to current timestamp
- **Primary Key**: (`follower_id`, `followee_id`)

### 6. Tags Table

- **Table Name**: `tags`
- **Description**: Stores tags that can be associated with photos.
- **Columns**:
  - `id`: INT, Primary Key, Auto Increment
  - `tag_name`: VARCHAR(255), Unique
  - `created_at`: TIMESTAMP, Default to current timestamp

### 7. Photo Tags Table

- **Table Name**: `photo_tags`
- **Description**: Stores the relationship between photos and tags.
- **Columns**:
  - `photo_id`: INT, Foreign Key referencing `photos(id)`
  - `tag_id`: INT, Foreign Key referencing `tags(id)`
- **Primary Key**: (`photo_id`, `tag_id`)

### Project Challenges
1. Finding the 5 oldest users
2. What days of the week do most users registered on.
3. Find the users who have never posted a photo
4. Find out the most likes in a single photo
5. Find number of users who have liked every single photo on the site
6. What are the top 5 most commonly used Hastags
   
## Installation

1. Clone the repository:
   git clone https://github.com/bssavinash202/Instagram_clone_database_mySQL.git
   
