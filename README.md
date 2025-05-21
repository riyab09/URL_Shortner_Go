# URL Shortner  (Golang + MongoDB)

A lightweight and scalable URL shortener built with **Golang**, using the **Gin web framework** and **MongoDB** for persistent storage. Shortens long URLs into compact links and redirects to the original destination.



##  Features

-  Random 6-character short code generator
-  Automatic short link creation and redirection
-  MongoDB-based persistent URL storage
-  RESTful API using Gin
-  Clean and modular project architecture
-  Fault-tolerant and scalable

---

##  Tech Stack

- **Language:** Golang
- **Framework:** Gin
- **Database:** MongoDB
- **Environment:** godotenv
- **Deployment Ready:** Yes

---

##  Folder Structure

<pre>
url_shortener/
├── constant/           # Constants like base URLs and route paths
│   └── constant.go
├── controller/         # URL logic handlers
│   └── UrlController.go
├── database/           # DB connection and query logic
│   ├── connection.go
│   └── dbcalls.go
├── helper/             # Utility functions (e.g., random string generation)
│   └── helper.go
├── router/             # Route and API versioning logic
│   ├── router.go
│   └── routes.go
├── types/              # Data models and request/response types
│   └── url_type.go
├── .env                # Environment variables (PORT, DB_HOST, etc.)
├── go.mod              # Go module definition
├── go.sum              # Go module checksum file
├── main.go             # App entry point
</pre>

---

## Getting Started

### Prerequisites

- Go 1.19+
- MongoDB instance (local or cloud)
- Git

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/url_shortener.git
   cd url_shortener

2. **Create a .env file**
```bash
PORT=8080
API_VERSION=/v1
DB_HOST=localhost:27017
```
3. **Run the application**
```bash
go run main.go
```

##  API Endpoints

| Method | Endpoint           | Description                     |
|--------|--------------------|---------------------------------|
| POST   | `/v1/url/shorten`  | Shortens a long URL             |
| GET    | `/v1/url/:code`    | Redirects to the original URL   |


## Sample Request – Shorten URL
```bash
POST /v1/url/shorten
{
  "long_url": "https://example.com/some/very/long/url"
}
```
## Sample Response
```json
{
  "short_url": "http://localhost:8080/v1/url/abc123"
}
```
## Testing
You can test endpoints using:
- Postman
- curl

## Postman
  Import the endpoints and make POST/GET requests.

## How It Works
- User sends a POST request with a long URL.
- Server generates a unique 6-character short code.
- MongoDB stores the mapping between long and short URLs.
- The shortened link is returned.
- When the short URL is accessed, the server redirects to the long URL.


