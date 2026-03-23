# Nginx Proxy Manager

Reverse proxy management with a web UI for managing proxy hosts, SSL certificates, redirection hosts, streams, and access lists.

## Usage

```bash
# Start Nginx Proxy Manager
docker compose up -d
```

## Ports

| Port | Purpose |
|------|---------|
| 80   | HTTP traffic |
| 443  | HTTPS traffic |
| 81   | Admin web UI and API |

## Default Login

On first launch, log in at `http://localhost:81` with:

- **Email:** `admin@example.com`
- **Password:** `changeme`

You will be prompted to change these on first login.

## CLI

Use the [nginxpm-cli](https://github.com/piyush-gambhir/nginxpm-cli) to manage this instance from the command line:

```bash
# Login
nginxpm login

# List proxy hosts
nginxpm proxy list -o json

# Create a proxy host from file
nginxpm proxy create -f proxy.json
```

## API

The REST API is available at `http://localhost:81/api/`.

- Health check: `GET /api/`
- Auth: `POST /api/tokens` with `{"identity": "email", "secret": "password"}`
- All endpoints require a Bearer JWT token obtained from the auth endpoint.

## Documentation

- [Nginx Proxy Manager Docs](https://nginxproxymanager.com/guide/)
- [API Reference](https://github.com/NginxProxyManager/nginx-proxy-manager)
