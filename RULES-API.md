# API contracts

Use the documented standalone broker JSON contract. DSH and Muse Bearer tokens
are distinct. Bind only loopback or Tailscale IPv4; read-only Tailnet access uses
the actual socket peer (100.64.0.0/10 or loopback), never forwarding headers.
A loopback proxy must itself remain private. No public proxy or Funnel.

Require exact owner/conversation scopes, stable event IDs and bounded context.
Reject oversize rather than silently truncate. Read cold DSH sessions through
the official read-only persistence handle, never resume an agent to export.

Persist send reservations before I/O; accept only real OneBot receipts. Ack only
confirmed sends. Unknown outcomes must not trigger a repeated POST. Ignore
inherited proxies, disallow redirects and preserve verified HTTPS where used.
