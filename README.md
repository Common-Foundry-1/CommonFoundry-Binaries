# Common Foundry Binaries

This is the official binary distribution repository for Common Foundry testing releases.

Application source code is intentionally not stored in this repository. GitHub's automatically generated **Source code** archives contain only this distribution metadata; installable builds are listed under [Releases](https://github.com/JustAResearcher/CommonFoundry-Binaries/releases).

## RCNet-1 release candidate

RC5 is a complete RCNet-1 testing release. You do not need to install an earlier
release candidate first. RCNet-1 is experimental, is not mainnet, and its coins
have no intended monetary value. The release does not claim an external audit
or independent reproduction of the cryptography.

- **Windows wallet:** install the RC5 `windows-x86_64-setup.exe`. On first use,
  allow the runtime preparation window to finish downloading and authenticating
  approximately 6.4 GB of public model data. This is not your wallet backup.
- **Portable wallet and node:** download the RC5 runtime bootstrap archive for
  your operating system, extract it, then run `START-WALLET.bat` on Windows or
  `./start-wallet.sh` on Linux. The included README explains runtime preparation.
  Linux also needs the wallet's GTK/WebKitGTK desktop libraries. No earlier RC
  installation is needed. Prefer this bootstrap package for Linux first use;
  the separate AppImage and deb builds do not run the Windows automatic setup.
- **Pool miners:** use the RC5 miner archive for your operating system and follow its
  included README. Windows mining uses WSL2; mining also requires a compatible
  NVIDIA GPU and a certificate-pinned pool URL.
- **Wallet solo mining:** use the complete runtime bootstrap archive. Close the
  wallet, run `PREPARE-MINING.bat` (Windows) or `./prepare-mining.sh` (Linux), then
  reopen the wallet and use the Mining tab. Allow 85 GB free for authenticated
  proving inputs and scratch space. The packaged workers target RTX 50-series;
  hardware qualification used an RTX 5090. CUDA 12.8 is required, along with
  WSL2 Ubuntu-22.04 on Windows. Other GPU architectures are not qualified.

RC5 fixes the minimum transaction fee at **0.1 CMFD**, adds native backup file
pickers, and connects wallet solo mining to the ProductionV4 proof workers.
All RCNet nodes must upgrade together: the fee rule changes the consensus
fingerprint. Empty RC4 chain directories preserve the wallet key while upgrading
metadata; existing block histories are never automatically reset. Mining cannot
start before RCNet's configured genesis.

The small bootstrap archives contain the wallet, node, and authenticated
downloader. The model data is fetched separately; keep the preparation window
open until authentication completes. Interrupted transfers can be resumed.
Reserve at least 16 GB of free space for wallet-only preparation: downloaded
chunks and the assembled 6.4 GB bank temporarily coexist.

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
