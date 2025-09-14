# How to delete a list of users from Google Analytics via the Google Management API
A Python script that will delete a list of users from Google Analytics via the Google Management API. A typical use case for this would be for security purposes when a list of user link ids are provided for deletion. More information can be found in the Google Management API documentation found [here](https://developers.google.com/analytics/devguides/config/mgmt/v3/mgmtReference/management/accountUserLinks/delete). The necessary Google client libary can be installed with `pip install google-api-python-client`.


# delete-users-google-analytics (ARCHIVED SNAPSHOT)

This repo intentionally preserves a 2016 approach for removing users from **Universal Analytics (UA)** using the v3 Management API. It is kept to show a snapshot of capability at the time. It is **not** a modern GA4 solution and is not maintained.

## What this repo is
- A historical snapshot of how I approached UA user removal around 2016.
- The original write-up and example are in [`legacy/`](./legacy/) and kept as-is.

## What this repo is not
- Not a GA4 solution.
- Not supported or updated. Security guidance below applies to anyone reading old examples.

## Today (high-level guidance)
- UA has been sunset. GA4 uses the **Analytics Admin API** for user administration.
- If you need to remove access in GA4 today, look for Admin API user methods for **accounts** or **properties**.
- Prefer JSON service accounts over P12, least-privilege OAuth scopes, and short-lived credentials.

## Why keep this?
It’s a portfolio snapshot: the code and approach reflect the ecosystem, libraries, and best practices I used then. I keep it to show progress over time.


## License
MIT — see [`LICENSE`](./LICENSE).
