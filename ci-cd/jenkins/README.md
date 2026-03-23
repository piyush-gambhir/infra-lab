# Jenkins

CI/CD automation server.

## Usage

```bash
docker compose up -d
```

## Ports

| Port  | Purpose |
|-------|---------|
| 8080  | Web UI and API |
| 50000 | Agent communication |

## Default Setup

Setup wizard is disabled via `JAVA_OPTS`. Jenkins starts with no authentication by default.

To create an API token for the CLI:
1. Go to `http://localhost:8080/user/admin/configure`
2. Add a new API token

## CLI

```bash
export JENKINS_URL=http://localhost:8080
export JENKINS_USER=admin
export JENKINS_TOKEN=<your-api-token>
jenkins status
```

## Documentation

- [Jenkins Docs](https://www.jenkins.io/doc/)
