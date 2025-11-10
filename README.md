###############################################
# 🐘 PostgreSQL DBA Tools – Complete Reference
###############################################

# 🔥 Most Commonly Used Tools (Every DBA Uses Daily)
psql             → Connect and run SQL queries interactively
pg_dump          → Logical backup tool (exports schema/data)
pg_restore       → Restore data from dump files created by pg_dump
pg_dumpall       → Dump all databases, roles, and tablespaces
createdb         → Create a new database
dropdb           → Delete an existing database
createuser       → Create a new database role/user
dropuser         → Delete an existing role/user
pg_isready       → Check if PostgreSQL is accepting connections

# ⚙️ Server Control / Management Tools
pg_ctl           → Start, stop, restart, reload PostgreSQL service
initdb           → Initialize a new PostgreSQL cluster
pg_basebackup    → Take a full physical backup (replication setups)
pg_rewind        → Re-sync standby with primary after failover
pg_resetwal      → Reset Write-Ahead Logs (emergency use)
pg_controldata   → Display cluster control info (System ID, checkpoints)
pg_upgrade       → Upgrade PostgreSQL cluster between versions

# 🔍 Monitoring / Inspection / Diagnostic Tools
pg_stat_activity → (view) Show current connections and queries
pg_stat_all_tables → (view) Show table-level stats
pg_stat_replication → (view) Show replication status
pgbench          → Benchmark tool for load testing performance
oid2name         → Map table OIDs to names (useful for recovery)
pg_archivecleanup → Clean old archived WAL files after backup

# 🧰 Advanced Maintenance & Replication Tools
pg_receivewal    → Stream WAL files from primary to standby
pg_recvlogical   → Receive logical replication changes from slot
pg_verifybackup  → Verify completeness of physical backups
pg_combinebackup → Combine multiple incremental backups
pg_waldump       → Display contents of WAL transaction logs

# 🧩 Build / Development / Information Tools
pg_config        → Show PostgreSQL build/config details
pg_test_fsync    → Test file synchronization speed
pg_test_timing   → Test system timing performance
ecpg             → C preprocessor for embedding SQL in C programs
pgbench-tools    → Framework for advanced benchmarking

# 🧮 Cluster & Replication (Advanced DBA Level)
pg_receivexlog   → (old name for pg_receivewal) Archive WALs
pg_receivewal    → Stream and archive WALs continuously
pg_basebackup    → Physical backup for replication
pg_rewind        → Fix desynchronized standby after failover

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
# Use 'psql --help' or 'pg_dump --help' to see 
# all available options and flags (-U, -d, -h, etc.)
###############################################
