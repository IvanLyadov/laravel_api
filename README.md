# Laravel Task API

Laravel 12 REST API for managing tasks.

## Requirements

- PHP 8.2+
- Composer
- MySQL or compatible database

## Setup

1. **Clone the repository:**
   ```sh
   git clone <your-repo-url>
   cd laravel_api
   ```

2. **Install dependencies:**
   ```sh
   composer install
   ```

3. **Copy `.env` and set up your environment:**
   ```sh
   cp .env.example .env
   ```
   - Set your database credentials in `.env`.

4. **Generate application key:**
   ```sh
   php artisan key:generate
   ```

5. **Run migrations:**
   ```sh
   php artisan migrate
   ```

6. **(Optional) Seed the database:**
   ```sh
   php artisan db:seed
   ```

7. **Start the development server:**
   ```sh
   php artisan serve
   ```
   The API will be available at `http://localhost:8000`.

## API Endpoints

| Method | Endpoint                | Description                | Body Parameters                |
|--------|-------------------------|----------------------------|--------------------------------|
| GET    | `/api/tasks`            | List all tasks             | –                              |
| POST   | `/api/tasks`            | Create a new task          | `name` (string, required),<br>`is_completed` (boolean, optional) |
| GET    | `/api/tasks/{id}`       | Get a single task          | –                              |
| PUT    | `/api/tasks/{id}`       | Update a task              | `name` (string, optional),<br>`is_completed` (boolean, optional) |
| DELETE | `/api/tasks/{id}`       | Delete a task              | –                              |

### Example Task Object

```json
{
  "id": 1,
  "name": "My Task",
  "is_completed": false
}
```

## CORS

CORS is enabled for all origins in `config/cors.php` for development.  
If you deploy to production, restrict allowed origins for security.

## Frontend Example

Make sure to call the API using the full URL, e.g.:
```js
fetch('http://localhost:8000/api/tasks')
```

## License

MIT