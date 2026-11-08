# Storage contracts

Private directories 0700 and credential/state files 0600. SQLite jobs and send
reservations are durable, with an exclusive process lock acquired before crash
reconciliation. The Node journal stores only routing/deduplication metadata.

Stable IDs are primary keys; conflicting payloads are rejected. Do not prune or
rewrite deduplication state automatically. An ack targets specific confirmed IDs
and does not imply erasure of retained SQLite history. No destructive migrations
or dual consumers; unknown sends remain blocked pending reconciliation.
