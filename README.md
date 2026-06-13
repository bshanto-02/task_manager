# ✦ TaskFlow — Task Manager

TaskFlow is a lightweight, clean, and beautiful web-based Task Management application built using **Python (Flask)**, native **HTML5**, and modern **CSS3**.

The application works entirely out-of-the-box with **zero external database dependencies**, storing tasks in an in-memory Python data structure. It is an excellent project for learning Flask fundamentals, routing, form handling, Jinja templating, and responsive web design.

---

## 🚀 Features

* Add new tasks instantly
* Mark tasks as completed or incomplete
* Delete tasks dynamically
* Real-time progress tracking
* Flash notifications for user actions
* Dark-mode futuristic UI
* Responsive layout for mobile and desktop
* No database setup required
* Beginner-friendly Flask architecture

---

## 📁 Project Structure

```text
TaskFlow/
│
├── app.py
├── requirements.txt
│
├── templates/
│   └── index.html
│
└── static/
    └── style.css
```

---

## 🛠 Technologies Used

* Python 3
* Flask
* HTML5
* CSS3
* Jinja2 Templates

---

## ⚙ Prerequisites

Before running the project, ensure that Python is installed on your system.

Check your Python version:

```bash
python --version
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## ▶ Running the Application

Start the Flask development server:

```bash
python app.py
```

After the server starts, open your browser and visit:

```text
http://127.0.0.1:5000
```

---

## 📡 Application Workflow

### GET /

Displays the main dashboard.

Responsibilities:

* Loads all existing tasks
* Calculates completed task count
* Renders progress percentage
* Shows an empty-state layout when no tasks exist

---

### POST /add

Creates a new task.

Form Field:

```html
<input type="text" name="task">
```

Validation Rules:

* Removes leading and trailing whitespace
* Rejects empty submissions

Success Response:

```python
{
    "id": int,
    "text": str,
    "done": False
}
```

---

### GET /toggle/<task_id>

Toggles task completion status.

Example:

```python
task["done"] = not task["done"]
```

Behavior:

* Marks task as completed
* Marks completed task as incomplete
* Redirects back to dashboard

---

### GET /delete/<task_id>

Deletes a task using Python list comprehension.

Example:

```python
tasks = [
    task for task in tasks
    if task["id"] != task_id
]
```

Behavior:

* Removes matching task
* Displays success notification
* Redirects back to dashboard

---

## 📊 Progress Tracking

TaskFlow automatically calculates completion progress.

Example Jinja expression:

```html
{{ (done_count / tasks|length * 100) | round }}%
```

This value updates dynamically whenever tasks are added, completed, or removed.

---

## 🎨 UI Design System

### Color Palette

| Variable  | Color   | Purpose            |
| --------- | ------- | ------------------ |
| --bg      | #0f1117 | Background         |
| --surface | #1a1d27 | Cards & Containers |
| --accent  | #6c63ff | Primary Accent     |
| --success | #3ecf8e | Completed Tasks    |
| --danger  | #ff5c5c | Delete Actions     |

---

## ✨ UI Features

### Animated Logo

The dashboard icon continuously rotates:

```css
animation: spin 8s linear infinite;
```

### Responsive Layout

For screens below 480px:

* Form elements stack vertically
* Task cards adjust automatically
* Improved mobile usability

---

## 🧠 Learning Concepts Covered

This project demonstrates:

### Flask

* Routing
* Request handling
* Redirects
* Flash messages
* Template rendering

### Python

* Lists
* Dictionaries
* Global state management
* List comprehensions
* Boolean state toggling

### Frontend

* Semantic HTML5
* CSS Variables
* Flexbox
* Responsive Design
* Animations

### Jinja2

* Loops
* Conditions
* Filters
* Dynamic calculations

---

## ⚠ Limitations

Because TaskFlow stores data in memory:

* Tasks are lost when the server stops
* Data is not persisted between restarts
* Not intended for production use

For persistence, consider integrating:

* SQLite
* PostgreSQL
* MySQL
* MongoDB

---

## 🔮 Future Improvements

* Task editing
* Due dates
* Task categories
* User authentication
* Database integration
* Dark/Light theme switching
* REST API support
* Task search and filtering

---

## 📜 License

This project is open-source and available for educational and personal use.

---

## 👨‍💻 Author

Created as a lightweight Flask learning project demonstrating task management workflows, dynamic templating, and responsive UI development.
