# 2025_ITCS6190_Assignment1

``` bash
acardioid@acardioid-uncc:~/CloudAsn/2025_ITCS6190_Assignment1$ make up
docker compose up --build
#1 [internal] load local bake definitions
#1 reading from stdin 1.08kB done
#1 DONE 0.0s

#2 [app internal] load build definition from Dockerfile
#2 transferring dockerfile: 173B done
#2 DONE 0.0s

#3 [db internal] load build definition from Dockerfile
#3 transferring dockerfile: 96B done
#3 DONE 0.0s

#4 [app internal] load metadata for docker.io/library/python:3.11-slim
#4 DONE 0.1s

#5 [db internal] load metadata for docker.io/library/postgres:16
#5 DONE 0.2s

#6 [app internal] load .dockerignore
#6 transferring context: 2B done
#6 DONE 0.0s

#7 [app 1/4] FROM docker.io/library/python:3.11-slim@sha256:1d6131b5d479888b43200645e03a78443c7157efbdb730e6b48129740727c312
#7 DONE 0.0s

#8 [app internal] load build context
#8 transferring context: 29B done
#8 DONE 0.0s

#9 [app 3/4] WORKDIR /app
#9 CACHED

#10 [app 2/4] RUN pip install --no-cache-dir psycopg[binary]==3.1.19
#10 CACHED

#11 [app 4/4] COPY main.py /app/
#11 CACHED

#12 [app] exporting to image
#12 exporting layers done
#12 writing image sha256:f654d05242bd8a37f40fabc695a579773f2357837fcf1f4d170997160769b7fa done
#12 naming to docker.io/library/2025_itcs6190_assignment1-app done
#12 DONE 0.0s

#13 [app] resolving provenance for metadata file
#13 DONE 0.0s

#14 [db internal] load .dockerignore
#14 transferring context: 2B done
#14 DONE 0.0s

#15 [db 1/2] FROM docker.io/library/postgres:16@sha256:3105ef2d654e4b216af23d8d71c85db7c490479e4ba4c10979883f806f247fdd
#15 DONE 0.0s

#16 [db internal] load build context
#16 transferring context: 30B done
#16 DONE 0.0s

#17 [db 2/2] COPY init.sql /docker-entrypoint-initdb.d/
#17 CACHED

#18 [db] exporting to image
#18 exporting layers done
#18 writing image sha256:12abcbdb13a2996a372323c44aad3dfe11fc8baa886758f213a14066cfe2a390 done
#18 naming to docker.io/library/2025_itcs6190_assignment1-db done
#18 DONE 0.0s

#19 [db] resolving provenance for metadata file
#19 DONE 0.0s
[+] Running 5/5
 ✔ 2025_itcs6190_assignment1-db               Built                                                                                    0.0s 
 ✔ 2025_itcs6190_assignment1-app              Built                                                                                    0.0s 
 ✔ Network 2025_itcs6190_assignment1_default  Created                                                                                  0.0s 
 ✔ Container 2025_itcs6190_assignment1-db-1   Created                                                                                  0.1s 
 ✔ Container 2025_itcs6190_assignment1-app-1  Created                                                                                  0.0s 
Attaching to app-1, db-1
db-1  | The files belonging to this database system will be owned by user "postgres".
db-1  | This user must also own the server process.
db-1  | 
db-1  | The database cluster will be initialized with locale "en_US.utf8".
db-1  | The default database encoding has accordingly been set to "UTF8".
db-1  | The default text search configuration will be set to "english".
db-1  | 
db-1  | Data page checksums are disabled.
db-1  | 
db-1  | fixing permissions on existing directory /var/lib/postgresql/data ... ok
db-1  | creating subdirectories ... ok
db-1  | selecting dynamic shared memory implementation ... posix
db-1  | selecting default max_connections ... 100
db-1  | selecting default shared_buffers ... 128MB
db-1  | selecting default time zone ... Etc/UTC
db-1  | creating configuration files ... ok
db-1  | running bootstrap script ... ok
db-1  | performing post-bootstrap initialization ... ok
db-1  | initdb: warning: enabling "trust" authentication for local connections
db-1  | initdb: hint: You can change this by editing pg_hba.conf or using the option -A, or --auth-local and --auth-host, the next time you run initdb.
db-1  | syncing data to disk ... ok
db-1  | 
db-1  | 
db-1  | Success. You can now start the database server using:
db-1  | 
db-1  |     pg_ctl -D /var/lib/postgresql/data -l logfile start
db-1  | 
db-1  | waiting for server to start....2025-09-07 22:04:34.028 UTC [49] LOG:  starting PostgreSQL 16.10 (Debian 16.10-1.pgdg13+1) on x86_64-pc-linux-gnu, compiled by gcc (Debian 14.2.0-19) 14.2.0, 64-bit
db-1  | 2025-09-07 22:04:34.030 UTC [49] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"
db-1  | 2025-09-07 22:04:34.033 UTC [52] LOG:  database system was shut down at 2025-09-07 22:04:33 UTC
db-1  | 2025-09-07 22:04:34.037 UTC [49] LOG:  database system is ready to accept connections
db-1  |  done
db-1  | server started
db-1  | CREATE DATABASE
db-1  | 
db-1  | 
db-1  | /usr/local/bin/docker-entrypoint.sh: running /docker-entrypoint-initdb.d/init.sql
db-1  | CREATE TABLE
db-1  | INSERT 0 6
db-1  | 
db-1  | 
db-1  | 2025-09-07 22:04:34.228 UTC [49] LOG:  received fast shutdown request
db-1  | waiting for server to shut down....2025-09-07 22:04:34.229 UTC [49] LOG:  aborting any active transactions
db-1  | 2025-09-07 22:04:34.231 UTC [49] LOG:  background worker "logical replication launcher" (PID 55) exited with exit code 1
db-1  | 2025-09-07 22:04:34.231 UTC [50] LOG:  shutting down
db-1  | 2025-09-07 22:04:34.232 UTC [50] LOG:  checkpoint starting: shutdown immediate
db-1  | 2025-09-07 22:04:34.288 UTC [50] LOG:  checkpoint complete: wrote 936 buffers (5.7%); 0 WAL file(s) added, 0 removed, 0 recycled; write=0.051 s, sync=0.003 s, total=0.057 s; sync files=306, longest=0.001 s, average=0.001 s; distance=4294 kB, estimate=4294 kB; lsn=0/19245C8, redo lsn=0/19245C8
db-1  | 2025-09-07 22:04:34.294 UTC [49] LOG:  database system is shut down
db-1  |  done
db-1  | server stopped
db-1  | 
db-1  | PostgreSQL init process complete; ready for start up.
db-1  | 
db-1  | 2025-09-07 22:04:34.347 UTC [1] LOG:  starting PostgreSQL 16.10 (Debian 16.10-1.pgdg13+1) on x86_64-pc-linux-gnu, compiled by gcc (Debian 14.2.0-19) 14.2.0, 64-bit
db-1  | 2025-09-07 22:04:34.347 UTC [1] LOG:  listening on IPv4 address "0.0.0.0", port 5432
db-1  | 2025-09-07 22:04:34.347 UTC [1] LOG:  listening on IPv6 address "::", port 5432
db-1  | 2025-09-07 22:04:34.349 UTC [1] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"
db-1  | 2025-09-07 22:04:34.352 UTC [67] LOG:  database system was shut down at 2025-09-07 22:04:34 UTC
db-1  | 2025-09-07 22:04:34.356 UTC [1] LOG:  database system is ready to accept connections
app-1  | === Summary ===
app-1  | {
app-1  |   "total_trips": 6,
app-1  |   "avg_fare_by_city": [
app-1  |     {
app-1  |       "city": "New York",
app-1  |       "avg_fare": 19.0
app-1  |     },
app-1  |     {
app-1  |       "city": "San Francisco",
app-1  |       "avg_fare": 20.25
app-1  |     },
app-1  |     {
app-1  |       "city": "Charlotte",
app-1  |       "avg_fare": 16.25
app-1  |     }
app-1  |   ],
app-1  |   "top_by_minutes": [
app-1  |     {
app-1  |       "city": "San Francisco",
app-1  |       "minutes": 28,
app-1  |       "fare": 29.3
app-1  |     },
app-1  |     {
app-1  |       "city": "New York",
app-1  |       "minutes": 26,
app-1  |       "fare": 27.1
app-1  |     },
app-1  |     {
app-1  |       "city": "Charlotte",
app-1  |       "minutes": 21,
app-1  |       "fare": 20.0
app-1  |     },
app-1  |     {
app-1  |       "city": "Charlotte",
app-1  |       "minutes": 12,
app-1  |       "fare": 12.5
app-1  |     },
app-1  |     {
app-1  |       "city": "San Francisco",
app-1  |       "minutes": 11,
app-1  |       "fare": 11.2
app-1  |     },
app-1  |     {
app-1  |       "city": "New York",
app-1  |       "minutes": 9,
app-1  |       "fare": 10.9
app-1  |     }
app-1  |   ]
app-1  | }

app-1 exited with code 0

```



Got it 👍 —here’s a clean, simple **README.md template** tailored to your assignment. You can copy this into your repo’s root and adjust minor details if needed.

---

# 🚀 Assignment #1: Docker Containers

This project demonstrates a simple **two-container Docker stack**:

* A **PostgreSQL database** seeded with trip data.
* A **Python application** that queries the database, computes statistics, and writes results to a JSON file.

It shows how to use Docker Compose for multi-container setups, environment variables, service networking, and reproducible workflows.

---

## 📦 Requirements

* [Docker](https://docs.docker.com/get-docker/)
* [Docker Compose](https://docs.docker.com/compose/) (usually included with Docker)
* [GNU Make](https://www.gnu.org/software/make/)

---

## ▶️ How to Run

From the project root:

```bash
# Build and run everything
make all

# Or just start stack (attached logs)
make up

# Run in background (if you added `up-detach`)
# make up-detach

# Stop and clean containers + volumes
make down
```

---

## 📂 Outputs

* Results are written to:

  ```
  out/summary.json
  ```
* The same summary is printed to stdout during execution.

---

## 📝 Example Output

**Terminal (stdout):**

```json
=== Summary ===
{
  "total_trips": 6,
  "avg_fare_by_city": [
    {"city": "Charlotte", "avg_fare": 16.25},
    {"city": "New York", "avg_fare": 19.0},
    {"city": "San Francisco", "avg_fare": 20.25}
  ],
  "top_by_minutes": [
    {"city": "San Francisco", "minutes": 28, "fare": 29.3},
    {"city": "New York", "minutes": 26, "fare": 27.1},
    {"city": "Charlotte", "minutes": 21, "fare": 20.0}
  ]
}
```

**File (`out/summary.json`):**

```json
{
  "total_trips": 6,
  "avg_fare_by_city": [...],
  "top_by_minutes": [...]
}
```

---

## ⚠️ Troubleshooting

* **DB not ready**: If the app says “Waiting for database…”, it’s normal—Compose waits until Postgres passes its healthcheck.
* **Password errors**: Ensure `DB_PASS` in `compose.yml` matches `POSTGRES_PASSWORD`.
* **Reset everything** (fresh DB, clean output):

  ```bash
  make clean
  make up
  ```
* **Permission issues on `/out`**: Ensure the `out/` folder is writable on your host:

  ```bash
  chmod 777 out
  ```

---

## 📚 Notes

* Press `Ctrl+C` to stop `make up` (attached mode).
* Use `make down` to remove containers and reset DB volumes.
* This project is part of *Cloud Computing for Data Analysis (ITCS 6190/8190, Fall 2025)*.
