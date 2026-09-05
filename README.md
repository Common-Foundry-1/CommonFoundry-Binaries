# Common Foundry Binaries

This is the official binary distribution repository for Common Foundry testing releases.

Application source code is intentionally not stored in this repository. GitHub's automatically generated **Source code** archives contain only this distribution metadata; installable builds are listed under [Releases](https://github.com/JustAResearcher/CommonFoundry-Binaries/releases).

## RCNet-1 release candidate

RC4 is a complete RCNet-1 testing release. You do not need to install an earlier
release candidate first. RCNet-1 is experimental, is not mainnet, and its coins
have no intended monetary value. The release does not claim an external audit
or independent reproduction of the cryptography.

- **Windows wallet:** install the RC4 `windows-x86_64-setup.exe`. On first use,
  allow the runtime preparation window to finish downloading and authenticating
  approximately 6.4 GB of public model data. This is not your wallet backup.
- **Portable wallet and node:** download the RC4 runtime bootstrap archive for
  your operating system, extract it, then run `START-WALLET.bat` on Windows or
  `./start-wallet.sh` on Linux. The included README explains runtime preparation
  and Linux desktop dependencies. No earlier RC installation is needed.
- **Miners:** use the RC4 miner archive for your operating system and follow its
  included README. Windows mining uses WSL2; mining also requires a compatible
  NVIDIA GPU and a certificate-pinned pool URL.

The small bootstrap archives contain the wallet, node, and authenticated
downloader. The model data is fetched separately; keep the preparation window
open until authentication completes. Interrupted transfers can be resumed.

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

Compare the result with the matching entry in `SHA256SUMS.txt`. Releases include
a detached OpenSSH signature, `SHA256SUMS.txt.sig`, over that exact manifest.
Authenticate it with the maintainer's independently trusted release public key;
a checksum alone does not authenticate the publisher. Windows executables are
not currently Authenticode-signed and may display an unknown-publisher warning.

## Tester feedback

Use this repository's Issues section for reproducible wallet, node, networking, or mining problems. Include the operating system, package filename, observed behavior, and relevant diagnostics. Never post wallet recovery material, private keys, passwords, or access tokens.
