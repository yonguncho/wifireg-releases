# WiFiReg releases

WiFiReg registers device MAC addresses on a Cisco AireOS wireless controller's local MAC filter,
reading the request from a JIRA ticket. An operator reviews every entry and presses the button;
nothing is registered automatically.

- Windows x64. No installer. Unzip and run `WiFiReg.exe`.
- Makes no outbound calls except to the controller (SSH) and the JIRA server you configure.
- Supports Cisco AireOS controllers with local MAC filtering (developed against a 5520 on 8.10).
  Catalyst 9800, other vendors, and RADIUS/ISE-based MAC authentication are not supported.
- The UI is in Korean.

## Download

Latest build: https://github.com/yonguncho/wifireg-releases/releases/latest

Check the download against `SHA256SUMS.txt` from the same release:

```powershell
(Get-FileHash .\WiFiReg-v0.1.0-win64.zip -Algorithm SHA256).Hash.ToLower()
```

## Status

v0.1.0 is the first public build. It passes its test suite against simulated controller and JIRA
responses. It has not yet been run against a production controller, so try it in a lab or on a
test SSID first.

Write-up: https://choiceguidelab.com
