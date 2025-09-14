# Archive rationale

This repository is intentionally frozen as a **museum piece** to document how I solved “delete users in Google Analytics (UA)” circa 2016.

- **Authenticity over retrofit:** No code modernization. The point is to show what I actually did then, not what I would do now.
- **Context first:** UA (v3) approaches don’t apply to GA4. Readers should treat this purely as historical reference.
- **Safety note:** Even when reading legacy examples, handle credentials and scopes carefully. See [`SECURITY.md`](./SECURITY.md).

If you’re doing this **today**:
- You’d target **GA4** via the **Analytics Admin API** (user links at the account/property level).
- You’d use JSON service accounts / user OAuth with least-privilege scopes and modern auth flows.
