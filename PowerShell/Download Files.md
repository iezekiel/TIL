1. Invoke-WebRequest

The first and most obvious option is the Invoke-WebRequest cmdlet. 
It is built into PowerShell and can be used in the following method:
```
$url = "http://mirror.internode.on.net/pub/test/10meg.test"
$output = "$PSScriptRoot\10meg.test"
Invoke-WebRequest -Uri $url -OutFile $output
```

2. System.Net.WebClient

A common .NET class used for downloading files is the System.Net.WebClient class.
```
$url = "http://mirror.internode.on.net/pub/test/10meg.test"
$output = "$PSScriptRoot\10meg.test"
$wc = New-Object System.Net.WebClient
$wc.DownloadFile($url, $output)
#OR
(New-Object System.Net.WebClient).DownloadFile($url, $output)
```

3. BITS Transfer

If you haven't heard of BITS before, check this out. 
BITS is primarily designed for asynchronous file downloads, but works perfectly fine synchronously too 
(assuming you have BITS enabled).
```
$url = "http://mirror.internode.on.net/pub/test/10meg.test"
$output = "$PSScriptRoot\10meg.test"
Import-Module BitsTransfer
Start-BitsTransfer -Source $url -Destination $output
#OR
Start-BitsTransfer -Source $url -Destination $output -Asynchronous
```