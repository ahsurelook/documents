# BULK block Inbound + Outbound Firewall Rules for windows

1) Type/Copy below snippet into a text document.
2) Change the folder location to whatever directy you would like to block all exe's from accessing the net.
2) Save it as <Whatever>.bat
3) Run as Admin

```
for %%G in ("C:\Program Files (x86)\Test Folder\*.exe") do (
  netsh advfirewall firewall add rule name="Blocked With Batchfile %%G" dir=in action=block program="%%G" enable=yes profile=any
  netsh advfirewall firewall add rule name="Blocked With Batchfile %%G" dir=out action=block program="%%G" enable=yes profile=any
)
```
