# Task Manager API

A simple task management REST API built with **Node.js**, **Express**, and **Supabase**. It supports CRUD operations on tasks and can be used as the backend for a to-do list or task tracking application.

## Features

- ✅ Fetch all tasks (with optional filtering by completion)
- 🔍 Fetch a specific task by ID
- ➕ Add a new task
- ✏️ Update an existing task
- ❌ Delete a task

## Technologies Used

- Node.js
- Express
- Supabase (PostgreSQL backend)
- EJS (view engine setup, although not currently used in the API)
- dotenv (for environment variable management)
- [Bruno](https://www.usebruno.com/) (for API testing)

## Getting Started

### Prerequisites

- Node.js (v14+)
- A Supabase project with a `tasks` table

### Tasks Table Schema

Ensure your `tasks` table has the following structure:

| Column      | Type     |
|-------------|----------|
| id          | UUID or SERIAL (Primary Key) |
| title       | Text     |
| description | Text     |
| complete    | Boolean  |

### Environment Variables

Create a `.env` file in the root directory with the following:

```
SUPABASE_URL=your_supabase_url
SUPABASE_KEY=your_supabase_anon_key
PORT=3000
```

### Installation

1. Clone the repository:

```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
```

2. Install dependencies:

```bash
npm install
```

3. Start the development server:

```bash
node index.js
```

## API Endpoints

### `GET /api/tasks`

Fetch all tasks.

**Optional Query Params:**

- `complete=true|false` — Filter by completion status.

### `GET /api/tasks/:id`

Fetch a single task by its ID.

### `POST /api/tasks`

Create a new task.

**Request Body:**

```json
{
  "title": "New Task",
  "description": "Details here",
  "complete": false
}
```

### `PUT /api/tasks/:id`

Update an existing task.

**Request Body:**

```json
{
  "title": "Updated Task",
  "description": "Updated description",
  "complete": true
}
```

### `DELETE /api/tasks/:id`

Delete a task by its ID.

## Testing the API

Use [Bruno](https://www.usebruno.com/) or any API testing tool (like Postman or Insomnia) to test the endpoints.

## License

This project is licensed under the MIT License.
