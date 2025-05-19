# Blog-Application-Project
## Project Overview
This project is a simple blogging platform developed using the Flask web framework. It is designed to allow users to manage their personal blog posts. Key operations include logging in, creating new posts, editing existing ones, and deleting posts. Posts are shown on the homepage in reverse chronological order and managed through a dashboard accessible after login.

## How It Works
When the application starts, it initializes a SQLite database that includes two main models: `User` and `Post`. A user logs in through the `/login` route using a username and password. Once authenticated, the user is directed to the `/dashboard`, where they can create new posts, view their post list, edit content, or delete entries. Posts are published by default and shown publicly on the homepage unless deleted. The logout route ends the session and redirects the user to the homepage.

## Data Model Description
- **User**: Represents an account that can log in to the application. Each user has a unique `username` and an associated `password`. The login is used to filter posts and grant access to the dashboard.
- **Post**: Represents a blog entry. Each post includes a `title`, `content`, `author` name (taken from the session), and `date_posted`. A `published` boolean flag is included to support potential future features like unpublishing.

The database schema supports one-to-many relationships, where one user can author many blog posts. All posts are timestamped and ordered by recency when displayed.

## Getting Started
1. Install dependencies with `pip install Flask Flask-SQLAlchemy`
2. Run the app using `python app.py`
3. Navigate to `http://localhost:5000` in your browser to begin using the blog.

This solution follows core Flask concepts and SQLAlchemy ORM principles, enabling a maintainable and extendable base for further blog features like permalinks, category tags, and multi-user support.
