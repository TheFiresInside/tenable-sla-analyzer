# Tenable SLA Analyzer

Signed Windows builds of a vulnerability-management SLA analysis tool that
consumes Tenable.io export data and produces SLA-aware dashboards, drill-downs,
and exports.

## Downloads

See the [Releases](../../releases) tab. Each release ships a single Windows
executable plus a `SHA256SUMS.txt`.

## Verifying a download

### Authenticode signature (PowerShell)
```powershell
Get-AuthenticodeSignature .\tenable_sla_analyzer_vNNN_windows.exe
# Status should be "Valid"; SignerCertificate Subject should include "Elliot Anstey".
```

### SHA256
```powershell
(Get-FileHash .\tenable_sla_analyzer_vNNN_windows.exe -Algorithm SHA256).Hash
# Compare against the value in SHA256SUMS.txt from the same release.
```

## First-run SmartScreen note

These builds are signed with an **Individual Validation** (IV) code-signing
certificate. On first run Windows Defender SmartScreen may show:

> *Windows protected your PC — this app is not commonly downloaded.*

This is the expected first-download experience for any IV-signed binary; it is
**not** a malware detection. Click **More info → Run anyway** to proceed. The
prompt fades as the publisher accumulates trusted download volume.

If you see a prompt that looks materially different (e.g. quarantined by
Microsoft Defender Antivirus, or `Status: NotTrusted` from `Get-AuthenticodeSignature`),
please open an issue.

## Author / contact

Builds signed by **Elliot Anstey** &lt;ea.infosec@gmail.com&gt; via SSL.com Code
Signing CA. Source code is not published in this repository; only built,
signed binaries are distributed here.
