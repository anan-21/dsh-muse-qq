# Changelog

## Unreleased

- Publish the DSH/Muse feature as an independent repository, extracted from
  `muse-qq-bridge` at `cdb4fccb5a41457c5d04b01854c1775c8d2e91f1`.
- Place code, installer, documentation and tests at repository-relative paths;
  add Linux/macOS CI without any dependency on the original bridge runtime.
- Preserve topic routing, scoped context, automatic return, private transport,
  durable send/ack contracts and the checksum-pinned upstream integration.
