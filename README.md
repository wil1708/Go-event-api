Go Event API

A robust and secure RESTful Event Management API built with Go, utilizing the Gin framework, JWT authentication, and SQLite persistence.

🛠️ Tech Stack & Dependencies

Language: Go (Golang)

Framework: Gin Gonic (HTTP Router & Web Framework)

Database & Persistence: SQLite (modernc.org/sqlite) with automatic table migration.

Authentication: JSON Web Tokens (golang-jwt/jwt/v5) and password hashing via bcrypt.

📁 Project Architecture

go-event-api/
├── api-test/         # HTTP request files for API testing (.http files)
├── db/               # Database initialization and SQLite configuration (api.db)
├── middlewares/      # Security & auth middlewares (JWT verification)
├── models/           # Domain business logic and data structures (User, Event, Registration)
├── routes/           # Presentation layer (HTTP controllers and endpoint routing)
├── utils/            # Shared utilities (JWT tokens generation/verification, bcrypt hashing)
├── go.mod            # Module definition and dependencies
├── go.sum            # Cryptographic hashes of dependencies
└── main.go           # Application entry point


🚀 Getting Started & Installation

Prerequisites

Go (version 1.20 or higher recommended)

Git

Setup & Run

Clone the repository:

git clone https://github.com/wil1708/Go-event-api.git


Run the application:

go run main.go


Note: Dependencies will be automatically fetched via go.mod. The embedded SQLite database (api.db) and schema tables will be initialized on startup.

The API server will run at http://localhost:8080.

🔌 API Endpoints & Testing (.http files)

This project includes a collection of .http request test files. You can execute these requests directly in your editor using the VS Code REST Client extension.

1. Public Routes

Get All Events: GET /events (get-events.http)

Get Event by ID: GET /events/{id} (get-single-event.http)

User Signup: POST /signup (create-user.http)

User Login: POST /login (login.http) — Returns a JWT token required for protected routes.

2. Protected Routes (Requires JWT Authorization Header)

Format: Authorization: <your_jwt_token>

Create Event: POST /events (create-event.http)

Update Event: PUT /events/{id} (update-event.http)

Delete Event: DELETE /events/{id} (delete-event.http)

Register for Event: POST /events/{id}/register (register.http)

Cancel Registration: DELETE /events/{id}/register (cancel-registration.http)

🔀 Git Workflow & Branching Strategy

This project follows a standard GitFlow branching methodology:

master: Production-ready and stable branch.

develop: Integration branch for ongoing feature developments.

