# ClickHouse

A fast open-source column-oriented OLAP database for real-time analytics.

## Start

```bash
docker compose up -d
```

## Connection

| Setting   | Value          |
| --------- | -------------- |
| HTTP      | localhost:8123 |
| Native    | localhost:9000 |
| User      | clickhouse     |
| Password  | clickhouse123  |

## Use it

Built-in SQL console (no extra tooling):

```
http://localhost:8123/play
```

Quick query over HTTP:

```bash
curl -s "http://clickhouse:clickhouse123@localhost:8123/" --data "SELECT version()"
```

Or with the bundled client:

```bash
docker compose exec clickhouse clickhouse-client --user clickhouse --password clickhouse123
```

## Replicate from Postgres (CDC)

ClickHouse can sync a Postgres database itself with the native
`MaterializedPostgreSQL` engine (logical-replication CDC), no external tooling.
Postgres must run with `wal_level=logical`, and ClickHouse needs
`allow_experimental_database_materialized_postgresql=1` (a `users.d` profile
setting). Then:

```sql
CREATE DATABASE pg_replica
ENGINE = MaterializedPostgreSQL('postgres:5432', 'mydb', 'user', 'password')
SETTINGS materialized_postgresql_tables_list = 'table_a,table_b';
```

ClickHouse snapshots the listed tables and streams ongoing changes. Query them as
`pg_replica.table_a`.
