# TA-CheckWindowsUpdates
Splunk app to invoke checks for missing windows updates and send results into Splunk for reporting.  Downloads most recent windows software update scan package (wsusscn2.cab) from specified s3 bucket.  

## Search Syntax:
```SPL
sourcetype="script:powershell" source=CheckWindowsUpdates
| table _time, host, source, ScanPackageDate, Title, MsrcSeverity, KBArticleIDs, RebootRequired, SecurityBulletinIDs, Description
| sort 0 - _time
```

## Sample Results:
![alt tag](https://github.com/dstaulcu/TA-CheckWindowsUpdates/blob/master/screenshots/spl_results.JPG)
