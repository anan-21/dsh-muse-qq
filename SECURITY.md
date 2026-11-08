# Security

- Use only a dedicated, authorized QQ account and a single configured private-chat
  owner. Keep one consumer for each queue.
- Bind the broker to loopback or its Tailscale IPv4 address. Never expose its port
  publicly or through Funnel. Read-only Tailnet routes authorize the real socket
  peer, ignoring forwarding headers; any loopback proxy must itself be private.
- Keep DSH and Muse tokens distinct, in owner-only files outside the repository.
  Do not put token values in chat, hook code, command arguments or logs.
- Enable context export explicitly. Default export is limited to the authorized
  private conversation; shared user memories need both documented opt-ins.
  Context files are conversation data and cannot grant additional tool access.
- Reserve sends before network I/O. Unknown outcomes require reconciliation,
  never automatic repetition. Ack only after a real receipt.
- Acknowledgement removes local pickup caches, not the retained SQLite audit
  payloads and deduplication history. Protect backups and retained state locally.

Do not include live configuration, chat records or secrets in public bug reports.
There is no live account deployment or stability guarantee in this repository.
