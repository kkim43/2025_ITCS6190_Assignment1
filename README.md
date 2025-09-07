# 2025_ITCS6190_Assignment1

## PDF Report
[📄 Report.pdf](./Report.pdf)

## What the stack does
This project runs two Docker containers: a PostgreSQL database with sample trip data and a Python app. The app reads from the database, calculates basic trip statistics, and saves the results to the console and to out/summary.json.

## Exact commands to run/stop
``` bash
# Build and start 
$ make all

# Start whole process 
$ make up

# Stop whole process and remove volumes
$ make down
```

## Example output (copy/paste)
``` bash

$ make down

docker compose down -v
[+] Running 3/3
 ✔ Container 2025_itcs6190_assignment1-app-1  Removed                      0.0s 
 ✔ Container 2025_itcs6190_assignment1-db-1   Removed                      0.0s 
 ✔ Network 2025_itcs6190_assignment1_default  Removed                      0.1s 


$ make up
docker compose up --build
#1 [internal] load local bake definitions
#1 reading from stdin 1.08kB done
#1 DONE 0.0s

...(omitted)...

#19 [db] resolving provenance for metadata file
#19 DONE 0.0s
[+] Running 5/5
 ✔ 2025_itcs6190_assignment1-db               Built                                                                                                                0.0s 
 ✔ 2025_itcs6190_assignment1-app              Built                                                                                                                0.0s 
 ✔ Network 2025_itcs6190_assignment1_default  Created                                                                                                              0.0s 
 ✔ Container 2025_itcs6190_assignment1-db-1   Created                                                                                                              0.0s 
 ✔ Container 2025_itcs6190_assignment1-app-1  Created                                                                                                              0.0s 
Attaching to app-1, db-1
db-1  | The files belonging to this database system will be owned by user "postgres".
db-1  | This user must also own the server process.

...(omitted)...

db-1  | 2025-09-07 22:43:31.342 UTC [1] LOG:  listening on IPv4 address "0.0.0.0", port 5432
db-1  | 2025-09-07 22:43:31.342 UTC [1] LOG:  listening on IPv6 address "::", port 5432
db-1  | 2025-09-07 22:43:31.344 UTC [1] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"
db-1  | 2025-09-07 22:43:31.348 UTC [66] LOG:  database system was shut down at 2025-09-07 22:43:31 UTC
db-1  | 2025-09-07 22:43:31.352 UTC [1] LOG:  database system is ready to accept connections
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

$ After interupt command by Ctrl + C

Gracefully Stopping... press Ctrl+C again to force
 Container 2025_itcs6190_assignment1-app-1  Stopping
 Container 2025_itcs6190_assignment1-app-1  Stopped
 Container 2025_itcs6190_assignment1-db-1  Stopping
db-1   | 2025-09-07 22:43:37.152 UTC [1] LOG:  received fast shutdown request
db-1   | 2025-09-07 22:43:37.153 UTC [1] LOG:  aborting any active transactions
db-1   | 2025-09-07 22:43:37.155 UTC [1] LOG:  background worker "logical replication launcher" (PID 69) exited with exit code 1
db-1   | 2025-09-07 22:43:37.156 UTC [64] LOG:  shutting down
db-1   | 2025-09-07 22:43:37.157 UTC [64] LOG:  checkpoint starting: shutdown immediate
db-1   | 2025-09-07 22:43:37.163 UTC [64] LOG:  checkpoint complete: wrote 6 buffers (0.0%); 0 WAL file(s) added, 0 removed, 0 recycled; write=0.002 s, sync=0.001 s, total=0.007 s; sync files=5, longest=0.001 s, average=0.001 s; distance=0 kB, estimate=0 kB; lsn=0/1924640, redo lsn=0/1924640
db-1   | 2025-09-07 22:43:37.167 UTC [1] LOG:  database system is shut down
 Container 2025_itcs6190_assignment1-db-1  Stopped


```

## Where outputs are written
Outputs are shown both in the process logs in terminal and in the file /out/summary.json.


## Troubleshooting
DB connection information only exists in the local .env file. If the repository is cloned, make sure to create a .env file and fill it with values like the example below:
``` env
POSTGRES_USER="   "
POSTGRES_PASSWORD="    " 
POSTGRES_DB="     "
```
