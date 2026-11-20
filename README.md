# WiFiReg releases

WiFiReg registers device MAC addresses on a Cisco AireOS wireless controller's local MAC filter.
It pulls pending requests from JIRA, lists them, and registers the ones an operator selects.

- Windows x64. No installer. Run `WiFiReg.exe`; it opens a page in your browser.
- The page is served on `127.0.0.1` only. Other machines cannot reach it.
- Makes no outbound calls except to the controller (SSH) and the JIRA server you configure.
- Supports Cisco AireOS controllers with local MAC filtering (developed against a 5520 on 8.10).
  Catalyst 9800, other vendors, and RADIUS/ISE-based MAC authentication are not supported.
- The UI is in Korean.

## Download

Single file (replace it to update; starts about 15 seconds slower because it unpacks itself):

https://github.com/yonguncho/wifireg-releases/releases/latest/download/WiFiReg.exe

Folder version (starts faster):

https://github.com/yonguncho/wifireg-releases/releases/latest/download/WiFiReg-win64.zip

Settings and history are kept in `%LOCALAPPDATA%\WiFiReg`, not next to the program, so either form can be
replaced with a newer one without losing them.

Check the download against `SHA256SUMS.txt` from the same release:

```powershell
(Get-FileHash .\WiFiReg-win64.zip -Algorithm SHA256).Hash.ToLower()
```

## First run

There is no site configuration in the package. On first run, open Settings and enter the controller
address and account and the JIRA URL and token, then press connect. The program lists the SSIDs and
request types it finds and fills in the rest from a recent ticket.

The launch link printed in the console works once. Press Enter in the console window for a new one. Account names, passwords and
tokens are typed in each time the program starts and are never written to disk.

## Status

The builds pass their test suite against simulated controller and JIRA responses. They have not
yet been run against a production controller, so try a lab or a test SSID first.

From v0.3.0 the code has also been through several rounds of independent review, with each finding
fixed and covered by a regression test.

Write-up: https://choiceguidelab.com/wifireg-wlc-mac-filter-registration/
