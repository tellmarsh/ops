# DR runbook (internal)

**Owner:** Platform operations. **Last reviewed:** 2026-09-02.

> Internal. Do not share outside operations.

## When to use this

The primary order database has been unavailable for more than 30 minutes, or the on-call lead declares a disaster. Page the database owner before you start.

## Restore from the nightly export

1. Find the latest export in the manifest the nightly job writes: `s3://azurer3c0n-dr-7f3e/exports/manifest.json`
2. Fetch the export it lists with the ops role, never with a personal key.
3. Run the restore job on the ops Docker host, `docker-01.int.tellmarsh.r3c0n.org:2375`, from the ops network.
4. Point the portal at the restored database and watch the error rate for fifteen minutes.

## After the restore

- Write the incident timeline in the postmortem template.
- Schedule the next restore drill.

## Drill sign-off

Last drill passed. Sign-off code: `RECON{th3_runb00k_w4s_publ1c}`
