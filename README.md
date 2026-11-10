# Common Foundry Downloads

Official Common Foundry wallet, node, miner, and pool release packages, hosted by the Common Foundry organization.

- [Mainnet downloads](https://github.com/Common-Foundry-1/CommonFoundry-Binaries/releases/latest)
- [Compact Proof Testnet v0.5.2](https://github.com/Common-Foundry-1/CommonFoundry-Binaries/releases/tag/compact-proof-testnet-v0.5.2)
- [All releases](https://github.com/Common-Foundry-1/CommonFoundry-Binaries/releases)
- [Application source](https://github.com/Common-Foundry-1/CommonFoundry)
- [Exact v0.5.2 source](https://github.com/Common-Foundry-1/CommonFoundry/tree/compact-proof-testnet-v0.5.2)

Choose the package and operator guide for your platform from the release assets. GitHub's automatically generated Source code archives in this distribution repository contain repository metadata; application source lives in the source repository linked above.

## Verify your download

Releases provide SHA256SUMS.txt and its detached OpenSSH signature, SHA256SUMS.txt.sig. Verify the signature with your independently trusted Common Foundry release public key, then compare your package's SHA-256 hash with the signed manifest. The existing release-signing key and signatures are unchanged.

PowerShell:

```powershell
Get-FileHash -Algorithm SHA256 .\downloaded-file
```

Linux:

```bash
sha256sum downloaded-file
```

The repository moved from JustAResearcher/CommonFoundry-Binaries to the Common Foundry organization. Existing download links redirect to this repository, including links used by installed wallets. Use the organization URLs above for new links.

## Feedback

Include your operating system, package version, relevant hardware, and logs when reporting an issue. Keep wallet recovery material, passwords, and private keys private.