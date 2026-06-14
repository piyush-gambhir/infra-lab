# Infra Lab

A collection of ready-to-use Docker Compose setups for popular databases, caches, messaging queues, search engines, observability tools, and vector databases. Each tool is organized in its own directory with a `docker-compose.yml` and a `README.md` for quick reference and usage instructions.

## Directory Structure

-   `caches/` — Memcached, Redis
-   `databases/` — ClickHouse, MariaDB, MongoDB, MySQL, PostgreSQL
-   `messaging-queues/` — Kafka, RabbitMQ
-   `observability/` — Grafana & Prometheus, Jaeger, SonarQube
-   `reverse-proxies/` — Nginx Proxy Manager
-   `search-engines/` — Elasticsearch, Meilisearch, Typesense
-   `vector-databases/` — ChromaDB, Qdrant, Weaviate

## How to Use

1. Navigate to the directory of the tool you want to run.
2. Review the `README.md` for specific instructions and configuration details.
3. Start the service using Docker Compose:

    ```powershell
    docker compose up -d
    ```

    Or, if the file is named `docker-compose.yaml`:

    ```powershell
    docker compose -f docker-compose.yaml up -d
    ```

4. Access the service using the ports and credentials described in the tool's `README.md`.

## Requirements

-   [Docker](https://www.docker.com/get-started)
-   [Docker Compose](https://docs.docker.com/compose/)

## Contributing

Feel free to submit pull requests or open issues for improvements, new tools, or bug fixes.

## License

MIT License
