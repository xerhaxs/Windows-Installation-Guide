# Windows 10 and 11 privat installation guide

## Boot ISO without network connection

### Windows 11 Bypass:

- Open CMD
```Shift + F10```

- Run in CMD to disable forced Microsoft Account login
```
OOBE\BYPASSNRO
``` 

- Allow Windows 11 installation
```
regedit
```

```
HKEY_LOCAL_MACHINE
    SYSTEM
        Setup
            rightclick -> new -> LabConfig     # create new dir "LabConifg"
                rightclick -> new -> DWORD-Value (32-Bit)     # set value to 1
                    BypassTPMCheck
                    BypassRAMCheck
                    BypassSecureBootCheck
                    BypassStorageCheck
                    BypassCPUCheck
```

- Allow Windows 11 upgrade from Windows 10 installation
```
HKEY_LOCAL_MACHINE
    SYSTEM
        Setup
            MoSetup
                AllowUpgradesWithUnsupportedTPMOrCPU # set value to 1
```

### Settings
- Select Language:  English (world)
- Version:  Windows 11 Pro N
- Select custom installation:
    - load Virt-Driver (if needed)
    - create partitions

### Bloadware + Spyware
- Run ```microsoftspy.reg``` to disable MS Spyware

- Run in PowerShell as Admin:
    ```
    notepad drivers\etc\hosts
    ```
- add Hosts:

```
127.0.0.1 a-0001.a-msedge.net
127.0.0.1 a.ads1.msn.com
127.0.0.1 a.ads2.msads.net
127.0.0.1 a.ads2.msn.com
127.0.0.1 a.rad.msn.com
127.0.0.1 ac3.msn.com
127.0.0.1 ad.doubleclick.net
127.0.0.1 adnexus.net
127.0.0.1 adnxs.com
127.0.0.1 ads1.msads.net
127.0.0.1 ads1.msn.com
127.0.0.1 ads.msn.com
127.0.0.1 aidps.atdmt.com
127.0.0.1 aka-cdn-ns.adtech.de
127.0.0.1 apps.skype.com
127.0.0.1 az361816.vo.msecnd.net
127.0.0.1 az512334.vo.msecnd.net
127.0.0.1 b.ads1.msn.com
127.0.0.1 b.ads2.msads.net
127.0.0.1 b.rad.msn.com
127.0.0.1 bs.serving-sys.com
127.0.0.1 c.atdmt.com
127.0.0.1 c.msn.com
127.0.0.1 cdn.atdmt.com
127.0.0.1 cds26.ams9.msecn.net
127.0.0.1 choice.microsoft.com
127.0.0.1 choice.microsoft.com.nsatc.net
127.0.0.1 compatexchange.cloudapp.net
127.0.0.1 corp.sts.microsoft.com
127.0.0.1 corpext.msitadfs.glbdns2.microsoft.com
127.0.0.1 cs1.wpc.v0cdn.net
127.0.0.1 cy2.vortex.data.microsoft.com.akadns.net
127.0.0.1 db3aqu.atdmt.com
127.0.0.1 df.telemetry.microsoft.com
127.0.0.1 diagnostics.support.microsoft.com
127.0.0.1 ec.atdmt.com
127.0.0.1 fe2.update.microsoft.com.akadns.net
127.0.0.1 feedback.microsoft-hohm.com
127.0.0.1 feedback.search.microsoft.com
127.0.0.1 feedback.windows.com
127.0.0.1 flex.msn.com
127.0.0.1 g.msn.com
127.0.0.1 h1.msn.com
127.0.0.1 h2.msn.com
127.0.0.1 i1.services.social.microsoft.com
127.0.0.1 i1.services.social.microsoft.com.nsatc.net
127.0.0.1 live.rads.msn.com
127.0.0.1 m.adnxs.com
127.0.0.1 m.hotmail.com
127.0.0.1 modern.watson.data.microsoft.com.akadns.net
127.0.0.1 msftncsi.com
127.0.0.1 msntest.serving-sys.com
127.0.0.1 oca.telemetry.microsoft.com
127.0.0.1 oca.telemetry.microsoft.com.nsatc.net
127.0.0.1 pre.footprintpredict.com
127.0.0.1 preview.msn.com
127.0.0.1 pricelist.skype.com
127.0.0.1 rad.live.com
127.0.0.1 rad.msn.com
127.0.0.1 redir.metaservices.microsoft.com
127.0.0.1 reports.wes.df.telemetry.microsoft.com
127.0.0.1 s.gateway.messenger.live.com
127.0.0.1 secure.adnxs.com
127.0.0.1 secure.flashtalking.com
127.0.0.1 services.wes.df.telemetry.microsoft.com
127.0.0.1 settings-sandbox.data.microsoft.com
127.0.0.1 sls.update.microsoft.com.akadns.net
127.0.0.1 sO.2mdn.net
127.0.0.1 sqm.df.telemetry.microsoft.com
127.0.0.1 sqm.telemetry.microsoft.com
127.0.0.1 sqm.telemetry.microsoft.com.nsatc.net
127.0.0.1 static.2mdn.net
127.0.0.1 statsfe1.ws.microsoft.com
127.0.0.1 statsfe2.update.microsoft.com.akadns.net
127.0.0.1 statsfe2.ws.microsoft.com
127.0.0.1 survey.watson.microsoft.com
127.0.0.1 telecommand.telemetry.microsoft.com
127.0.0.1 telecommand.telemetry.microsoft.com.nsatc.net
127.0.0.1 telemetry.appex.bing.net
127.0.0.1 telemetry.appex.bing.net:443
127.0.0.1 telemetry.microsoft.com
127.0.0.1 telemetry.urs.microsoft.com
127.0.0.1 ui.skype.com
127.0.0.1 v10.vortex-win.data.microsoft.com
127.0.0.1 view.atdmt.com
127.0.0.1 vortex-sandbox.data.microsoft.com
127.0.0.1 vortex-win.data.microsoft.com
127.0.0.1 vortex.data.microsoft.com
127.0.0.1 watson.live.com
127.0.0.1 watson.microsoft.com
127.0.0.1 watson.ppe.telemetry.microsoft.com
127.0.0.1 watson.telemetry.microsoft.com
127.0.0.1 watson.telemetry.microsoft.com.nsatc.net
127.0.0.1 wes.df.telemetry.microsoft.com
127.0.0.1 www.msftncsi.com
```

### Disable services:
- Login-Assisten for Microsoft-Accounts: disabled
- Windows-Biometricsservice: disabled

### Security Settings
- Put Windows Defender in Sandbox Mode:
    - Run in PowerShell as Admin:
        ```
        setx /M MP_FORCE_USE_SANDBOX 1
        ```

### Remove Bloadware:
- Edge:
    - Run in PowerShell as Admin:
        ```
        cd 'C:\Program Files (x86)\Microsoft\Edge\Application\*\Installer'
        ./setup.exe --uninstall --system-level --verbose-logging --force-uninstall
        ```

- Teams:
    ```
    Get-AppxPackage -Name MicrosoftTeams | Remove-AppxPackage
    ```

- Internetexplorer 11
    ```Control Panel > Programs > Programs and Features > Enable or disable Windows features:``` <br>
    ```Internetexplorer 11 disable```

- Uninstall unnecessary programs (optional)

- Create a Snapshot (optional)

- Enable network:

- CTT Program ```https://github.com/ChrisTitusTech/winutil``` (Run in PowerShell as Admin:):
    ```
    irm "https://christitus.com/win" | iex
    ```

### Windows Activation

- Public Windows activation keys:

```
Home: TX9XD-98N7V-6WMQ6-BX7FG-H8Q99
Home N: 3KHY7-WNT83-DGQKR-F7HPR-844BM
Home Single Language: 7HNRX-D7KGG-3K4RQ-4WPJ4-YTDFH
Home Country Specific: PVMJN-6DFY6-9CCP6-7BKTT-D3WVR
Professional: W269N-WFGWX-YVC9B-4J6C9-T83GX
Professional N: MH37W-N47XK-V7XM9-C7227-GCQG9
Education: NW6C2-QMPVW-D7KKK-3GKT6-VCFB2
Education N: 2WH4N-8QGBV-H22JP-CT43Q-MDWWJ
Enterprise: NPPR9-FWDCX-D2C8J-H872K-2YT43
Enterprise N: DPH2V-TTNVB-4X9Q3-TJR4H-KHJW4
```

- Run in CMD as Admin:
```
    slmgr /ipk <YOURLICENSEKEY>
        slmgr /skms kms8.msguides.com
            slmgr /ato
```            

- Or with:

```
irm https://get.activated.win | iex
```


