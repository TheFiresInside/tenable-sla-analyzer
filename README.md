# SLA Analyzer for Tenable.io

A third-party desktop application for tracking SLA compliance on
vulnerability findings retrieved from a Tenable.io tenant. Signed
Windows builds are published here for direct-download distribution.

> **Not affiliated with, endorsed by, or sponsored by Tenable, Inc.**
> "Tenable" and "Tenable.io" are trademarks of Tenable, Inc. Used here
> under nominative fair use solely to identify the third-party platform
> with which this application is designed to interoperate.

## Downloads

See the [Releases](../../releases) tab. Each release ships a single
Windows executable plus a `SHA256SUMS.txt`.

The Microsoft Store edition of this product (Store ID `9N94QX8NNFJ1`)
is also available; it is the same compiled application wrapped in an
MSIX package and re-signed by Microsoft.

## About the auto-generated "Source code" archives

GitHub automatically attaches `Source code (zip)` and `Source code (tar.gz)`
to every release. **These archives contain only this README — no
application source code is published in this repository or any of its
release assets.**

The application is distributed exclusively as built, signed binaries.
The source code is closed and is not hosted on GitHub. There is no
upstream / parent repository, no fork relationship, no template
relationship, and no webhook connecting this repository to any
source-bearing system.

## Verifying a download

### Authenticode signature (PowerShell)
```powershell
Get-AuthenticodeSignature .\<downloaded-file>.exe
# Status should be "Valid"; SignerCertificate Subject should include "Elliot Anstey".
```

### SHA256
```powershell
(Get-FileHash .\<downloaded-file>.exe -Algorithm SHA256).Hash
# Compare against the value in SHA256SUMS.txt from the same release.
```

## First-run SmartScreen note

These builds are signed with an **Individual Validation** (IV)
code-signing certificate. On first run Windows Defender SmartScreen
may show:

> *Windows protected your PC — this app is not commonly downloaded.*

This is the expected first-download experience for any IV-signed
binary; it is **not** a malware detection. Click **More info → Run
anyway** to proceed. The prompt fades as the publisher accumulates
trusted download volume.

If you see a prompt that looks materially different (e.g. quarantined
by Microsoft Defender Antivirus, or `Status: NotTrusted` from
`Get-AuthenticodeSignature`), please open an issue.

## Privacy

The application does not collect telemetry, usage analytics, crash
reports, or advertising identifiers. All processing happens on the
local machine. Full privacy policy:
https://thefiresinside.github.io/tenable-sla-analyzer-legal/

## Author / contact

Builds signed by **Elliot Anstey** &lt;ea.infosec@gmail.com&gt; via SSL.com
Code Signing CA.
