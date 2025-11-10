###############################################
# 🐘 PostgreSQL DBA Tools – Complete with Examples
###############################################

# 🔥 Most Commonly Used Tools (Every DBA Uses Daily)
psql             → Connect and run SQL queries interactively
Example: psql -h localhost -p 5432 -U postgres -d company

pg_dump          → Logical backup tool (exports schema/data)
Example: pg_dump -U postgres -d company -f /tmp/company.dump

pg_restore       → Restore data from dump files created by pg_dump
Example: pg_restore -U postgres -d company /tmp/company.dump

pg_dumpall       → Dump all databases, roles, and tablespaces
Example: pg_dumpall -U postgres > /tmp/full_backup.sql

createdb         → Create a new database
Example: createdb -U postgres testdb

dropdb           → Delete an existing database
Example: dropdb -U postgres testdb

createuser       → Create a new database role/user
Example: createuser -U postgres appuser

dropuser         → Delete an existing role/user
Example: dropuser -U postgres appuser

pg_isready       → Check if PostgreSQL is accepting connections
Example: pg_isready -h localhost -p 5432

###############################################
# ⚙️ Server Control / Management Tools
###############################################

pg_ctl           → Start, stop, restart, reload PostgreSQL service
Example: pg_ctl restart -D /var/lib/pgsql/16/data

initdb           → Initialize a new PostgreSQL cluster
Example: initdb -D /var/lib/pgsql/16/data

pg_basebackup    → Take a full physical backup (for replication)
Example: pg_basebackup -D /backup -Fp -Xs -P -U repl

pg_rewind        → Re-sync standby with primary after failover
Example: pg_rewind --target-pgdata=/data --source-server="host=10.0.0.1 dbname=postgres user=repl"

pg_resetwal      → Reset Write-Ahead Logs (emergency use only)
Example: pg_resetwal /var/lib/pgsql/16/data

pg_controldata   → Display cluster control info (System ID, checkpoints, etc.)
Example: pg_controldata /var/lib/pgsql/16/data

pg_upgrade       → Upgrade PostgreSQL cluster between versions
Example: pg_upgrade -b /old/bin -B /new/bin -d /data/old -D /data/new

###############################################
# 🔍 Monitoring / Inspection / Diagnostic Tools
###############################################

# (These are often used inside psql, not from shell)
pg_stat_activity → View current connections & queries
Example: SELECT * FROM pg_stat_activity;

pg_stat_all_tables → View table-level stats
Example: SELECT * FROM pg_stat_all_tables;

pg_stat_replication → View replication status
Example: SELECT * FROM pg_stat_replication;

pgbench          → Benchmark/load test PostgreSQL
Example: pgbench -i -s 10 company

oid2name         → Map table OIDs to table names (for recovery)
Example: oid2name -d company

pg_archivecleanup → Clean up old archived WAL files
Example: pg_archivecleanup /archive 000000010000000A000000FE

###############################################
# 🧰 Advanced Maintenance & Replication Tools
###############################################

pg_receivewal    → Stream WAL files from primary to standby
Example: pg_receivewal -D /wal_archive -h primary_host -U repl

pg_recvlogical   → Receive logical replication changes
Example: pg_recvlogical -d company -S slot1 --start -f -

pg_verifybackup  → Verify that a physical backup is complete
Example: pg_verifybackup /backup/2025-11-10

pg_combinebackup → Combine incremental backups into one
Example: pg_combinebackup /backup/full /backup/inc1 /backup/inc2

pg_waldump       → Display contents of WAL transaction logs
Example: pg_waldump /data/pg_wal/000000010000000A000000B2

###############################################
# 🧩 Build / Development / Information Tools
###############################################

pg_config        → Show PostgreSQL build/config details
Example: pg_config --version

pg_test_fsync    → Test file synchronization speed
Example: pg_test_fsync

pg_test_timing   → Test timing performance of your system
Example: pg_test_timing

ecpg             → C preprocessor for embedding SQL in C programs
Example: ecpg myprogram.pgc

pgbench-tools    → Framework for advanced benchmarking (optional)
Example: pgbench-tools run

###############################################
# 🧮 Cluster & Replication (Advanced DBA Level)
###############################################

pg_receivexlog   → (Old name for pg_receivewal) Archive WALs
Example: pg_receivexlog -D /wal_archive

pg_receivewal    → Stream and archive WALs continuously
Example: pg_receivewal -D /wal_archive -h primary -U repl

pg_basebackup    → Take a physical backup for replication
Example: pg_basebackup -D /backup -Fp -Xs -P

pg_rewind        → Fix desynchronized standby after failover
Example: pg_rewind --target-pgdata=/data --source-server="host=10.0.0.1 dbname=postgres user=repl"

###############################################
# ✅ Learning Priority (for New DBAs)
###############################################
1. psql
2. pg_dump / pg_restore / pg_dumpall
3. createdb / dropdb / createuser / dropuser
4. pg_ctl / pg_isready / initdb
5. pg_basebackup / pg_rewind / pg_controldata
6. pg_archivecleanup / pg_waldump
7. pg_upgrade / pg_verifybackup / pg_combinebackup
8. Diagnostic tools: pgbench / pg_test_fsync / pg_test_timing

###############################################
# 🏁 Tip:
# Use '--help' with any tool for full syntax:
# Example: psql --help  or  pg_dump --help
###############################################
