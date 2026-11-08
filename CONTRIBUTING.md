# Contributing

Use an isolated feature branch (`codex/` is used for automation), then a reviewed
pull request. Keep the changes source-only: never commit real chats, runtime
databases, credentials, private hostnames or personal Git identities.

Python 3.12+ and Node.js 24 are sufficient; runtime code uses their standard
libraries. The Muse shell-hook test additionally needs Bash and jq.

```bash
python3 -m unittest discover -s . -p 'test_*.py' -v
python3 -m unittest discover -s integration -p 'test_*.py' -v
node --test client/*.test.mjs integration/test_*.mjs
python3 -m compileall -q .
bash -n muse-inbox.sh
git diff --check
```

Test changes to integration against the pinned upstream fixture; update pins
only after auditing actual upstream source. Preserve exact owner scopes, private
transport, read-only context access and no-repeat handling for unknown sends.
Offline fixtures cannot establish that real QQ or Muse accounts are connected.
