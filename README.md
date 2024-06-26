
# Project Management Tool API


This project is a RESTful API for managing users, projects, tasks, and comments using Django and Django REST Framework.


## Requirements
- Python 3.10+
- Django 4.2
- Django REST Framework
- simplejwt==5.3.1

## Installation

```bash
git clone https://github.com/yourusername/project_management_tool.git
cd project_management_tool
python3 -m venv venv
source venv/bin/activate  
# On Windows use: venv\Scripts\activate
pip install -r requirements.txt
python manage.py makemigrations
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver

```
# API Endpoints
## Users

- Register User (POST /api/users/register/): Create a new user.

Request:

```bash
{
    "username": "newuser",
    "email": "newuser@example.com",
    "password": "securepassword123",
    "first_name": "New",
    "last_name": "User"
}
```

Login User (POST /api/users/login/): Authenticate a user and return a token.

Request:


```bash
{
    "username": "newuser",
    "password": "securepassword123"
}
```
- Get User Details (GET /api/users/{id}/): Retrieve details of a specific user.

- Update User (PUT/PATCH /api/users/{id}/): Update user details.

Request:


```bash
{
    "first_name": "Updated",
    "last_name": "Name"
}
```
- Delete User (DELETE /api/users/{id}/): Delete a user account.

## Projects
- List Projects (GET /api/projects/): Retrieve a list of all projects.

- Create Project (POST /api/projects/): Create a new project.

Request:


```bash
{
    "name": "New Project",
    "description": "Description of the new project",
    "owner": 1
}
```
- Retrieve Project (GET /api/projects/{id}/): Retrieve details of a specific project.

- Update Project (PUT/PATCH /api/projects/{id}/): Update project details.

Request:


```bash
{
    "name": "Updated Project",
    "description": "Updated description of the project"
}
```
- Delete Project (DELETE /api/projects/{id}/): Delete a project.

## Tasks
- List Tasks (GET /api/projects/{project_id}/tasks/): Retrieve a list of all tasks in a project.

- Create Task (POST /api/projects/{project_id}/tasks/): Create a new task in a project.

Request:


```bash
{
    "title": "New Task",
    "description": "Description of the new task",
    "status": "To Do",
    "priority": "Medium",
    "assigned_to": 1,
    "due_date": "2024-12-31T23:59:59Z"
}
```
- Retrieve Task (GET /api/tasks/{id}/): Retrieve details of a specific task.

- Update Task (PUT/PATCH /api/tasks/{id}/): Update task details.

Request:


```bash
{
    "status": "In Progress",
    "priority": "High"
}
```
- Delete Task (DELETE /api/tasks/{id}/): Delete a task.

## Comments
- List Comments (GET /api/tasks/{task_id}/comments/): Retrieve a list of all comments on a task.

- Create Comment (POST /api/tasks/{task_id}/comments/): Create a new comment on a task.

Request:


```bash
{
    "content": "This is a new comment",
    "user": 1
}
```
- Retrieve Comment (GET /api/comments/{id}/): Retrieve details of a specific comment.

- Update Comment (PUT/PATCH /api/comments/{id}/): Update comment details.

Request:


```bash
{
    "content": "Updated comment content"
}
```
- Delete Comment (DELETE /api/comments/{id}/): Delete a comment.
