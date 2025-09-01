# The Appalachian Footpath Box Solve

This repo publishes **cryptographic proofs of existence** for solves of The Appalachian Footpath Box location from the book [There’s Treasure Inside](https://treasureinside.com/).  No plaintext content is published here until a later reveal. Verification steps are provided for when that happens.

## What’s in here
- `proofs/v1.0.0/solve-v1.0.0.tar.gz.sha256` — SHA-256 digest of the archive
- `proofs/v1.0.0/solve-v1.0.0.tar.gz.sha256.ots` — OpenTimestamps proof (independent time)
- `proofs/v1.0.0/solve-v1.0.0.tar.gz.sha256.asc` — Authorship signature

> Publishing a hash proves existence-by-time. It does **not** reveal or license the underlying content.

## After the reveal: how to verify

1) Verify the SHA-256 matches the archive when revealed:
   ```bash
   sha256sum solve-v1.0.0.tar.gz
   cat proofs/solve-v1.0.0.tar.gz.sha256

2) Verify the timestamp (independent proof of time):
   ```bash
   ots verify proofs/solve-v1.0.0.tar.gz.sha256

3) Verify authorship signature:
   ```bash
   gpg --verify proofs/solve-v1.0.0.tar.gz.sha256.asc proofs/solve-v1.0.0.tar.gz.sha256

4) Extract & view solve contents
   ```bash
   mkdir -p reveal && tar -xzf solve-v1.0.0.tar.gz -C reveal
