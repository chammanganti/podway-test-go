# Go Chi — Podway Template

A minimal Go HTTP API using the Chi router, pre-configured to deploy on Podway.

## What's included

- Go 1.22
- Chi router v5
- `/health` endpoint (required by Podway for health checks)
- Listens on port 8080 (Podway default)
- Multi-stage Dockerfile for minimal image size

## Getting started

1. Deploy this template from the Podway dashboard
2. Podway will fork this repo to your GitHub account
3. Your first build will trigger automatically

## Customizing

Add your routes in `main.go`:

```go
r.Get("/api/users", func(w http.ResponseWriter, r *http.Request) {
    json.NewEncoder(w).Encode([]string{})
})
```

## Environment variables

Set environment variables in Podway's dashboard under your environment's **Configuration** tab.

Access them in your app:

```go
dbURL := os.Getenv("DATABASE_URL")
```

## Health check

Podway uses `GET /health` to verify your app is running. Keep this endpoint returning a 200 response.
