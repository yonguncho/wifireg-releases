# WiFiReg releases

WiFiReg registers device MAC addresses on a Cisco AireOS wireless controller's local MAC filter.
It pulls pending requests from JIRA, lists them, and registers the ones an operator selects.

- Windows x64. No installer. Unzip and run `WiFiReg.exe`; it opens a page in your browser.
- The page is served on `127.0.0.1` only. Other machines cannot reach it.
- Makes no outbound calls except to the controller (SSH) and the JIRA server you configure.
- Supports Cisco AireOS controllers with local MAC filtering (developed against a 5520 on 8.10).
  Catalyst 9800, other vendors, and RADIUS/ISE-based MAC authentication are not supported.
- The UI is in Korean.

## Download

https://github.com/yonguncho/wifireg-releases/releases/latest/download/WiFiReg-win64.zip

Check the download against `SHA256SUMS.txt` from the same release:

```powershell
(Get-FileHash .\WiFiReg-win64.zip -Algorithm SHA256).Hash.ToLower()
```

## First run

There is no site configuration in the package. On first run the Settings page opens; enter your
controller address, JIRA URL, field names and status names there. Account names, passwords and
tokens are typed in each time the program starts and are never written to disk.

## Status

The builds pass their test suite against simulated controller and JIRA responses. They have not
yet been run against a production controller, so try a lab or a test SSID first.

Write-up: https://choiceguidelab.com/wifireg-wlc-mac-filter-registration/
