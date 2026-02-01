# Blogsite – Part 4 (User Authentication + Comments + Role-Based Access)

This final part brings full user management and security to the blog platform. Instead of letting anyone create or modify posts, the app now supports registration, login, logout, and access control. Every user has an account stored in the database, with hashed passwords and session handling managed cleanly by `Flask-Login`.

Only authenticated users can write comments on posts, and only the admin user is allowed to create, edit, or delete blog posts. The app protects these routes with decorators, returning proper HTTP errors for unauthorized access. Passwords are stored securely using Werkzeug hashing, and user sessions persist across pages once logged in.

Comments are stored in their own database table and linked to both the user and the blog post via SQLAlchemy relationships. CKEditor is still used for rich-text editing, but now each comment and post is tied directly to the authenticated user who created it.

The site now behaves like a real blogging platform: anyone can read posts, view comments, and browse the site, while only registered users can interact. The admin-only routes ensure safe content management without exposing edit/delete actions to the public.

Skills learned: implementing full authentication with Flask-Login, securing routes with decorators, hashing passwords securely, working with linked SQLAlchemy models, managing user sessions, adding comment functionality, restricting features based on roles, and integrating all of this into a clean Flask + Bootstrap application.
