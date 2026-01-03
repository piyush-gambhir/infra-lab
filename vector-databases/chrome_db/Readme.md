# Chroma Vector Database with Docker Compose

This repository contains a simple Docker Compose setup for running [Chroma](https://www.trychroma.com/) with persistent storage.

---

## Prerequisites

- Docker Engine ≥ 19.03
- Docker Compose ≥ 1.27
- (Optional) `make` for convenience commands

---

## Getting Started

1. **Clone or copy** this folder to your machine.

2. **Start Chroma**

   ```bash
   docker-compose up -d
   ```

   - Pulls the `chromadb/chroma:1.4.0` image
   - Exposes port:
     - `8000` for REST API

3. **Verify**
   ```bash
   docker-compose ps
   ```
   You should see the `chromadb` service running.

---

## Accessing Chroma

- **REST API**:  
  http://localhost:8000

---

## Persistent Storage

Data is stored in the Docker volume `chroma-data`, which maps to `/data` inside the container. Even if you recreate or upgrade the service, your collections and data remain intact.

- **Inspect volume location** (host):
  ```bash
  docker volume inspect chromedb_chroma-data
  ```

---

## Common Commands

- **Stop and remove containers** (preserves data):
  ```bash
  docker-compose down
  ```
- **Stop, remove, and delete volumes** (dangerous—data loss):
  ```bash
  docker-compose down -v
  ```
- **View logs**:
  ```bash
  docker-compose logs -f chromadb
  ```

---

## Documentation

- [Chroma Documentation](https://docs.trychroma.com/)
