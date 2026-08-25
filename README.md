# Common Foundry Binaries

This is the official binary distribution repository for Common Foundry testing releases.

Application source code is intentionally not stored in this repository. GitHub's automatically generated **Source code** archives contain only this distribution metadata; installable builds are listed under [Releases](https://github.com/JustAResearcher/CommonFoundry-Binaries/releases).

## Current testing scope

- Devnet builds use the existing Common Foundry Devnet-0 network.
- Production and mainnet activation remain disabled.
- These builds are for wallet, node, peer-sync, transaction, and mining tests.
- Mainnet source, configuration, and launch binaries are not distributed here before launch.

## Download verification

Each release includes `SHA256SUMS.txt` and `BUILDINFO.json`. Verify a downloaded file before running it.

PowerShell:

```powershell
Get-FileHash -Algorithm SHA256 .\downloaded-file
```

Linux:

```bash
sha256sum downloaded-file
```

Compare the result with the matching entry in `SHA256SUMS.txt`. Release tags are signed by the Common Foundry release maintainer. Windows executables are not currently code-signed and may display an unknown-publisher warning.

## Tester feedback

Use this repository's Issues section for reproducible wallet, node, networking, or mining problems. Include the operating system, package filename, observed behavior, and relevant diagnostics. Never post wallet recovery material, private keys, passwords, or access tokens.
