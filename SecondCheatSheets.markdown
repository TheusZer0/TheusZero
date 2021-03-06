---
layout: post
title: "Linux"
author: "TheusZero"
subtitle: 'Codigos mas usados'
header-img: "images/Sekiro3.png"
catalog: true
comments: true
---
#### Sudo 

```Python
sudo -l
```

```Python
sudo -u USER /bin/bash
```

```Python
sudo -u USER commandLine /dir/file
```
#### Net
```Python
sockstat -4 -l 
```
```Python
netstat -anp tcp | grep -i listen
```
#### DNS

**add the dns server to your machine**

```Python
echo "Mensaje" | sudo tee -a /dir/archivo 
```

#### Echo

**escribir sin vim**
```Python
echo “Reverse shell” > /dir/file
```
#### Perl

```Python
sudo perl -e 'exec "/bin/sh";
```
#### SSH

**El punto tambien va del final.**
```Python
sshpass -p 'passwordOfUser' scp -oStrictHostKeyChecking=no User@IP:File .
```

**Port Forwarding Desde mi maquina**
```Python
ssh -L port:127.0.0.1:port -N -f -l userSSH IP 
```

**ssh-passwd fuerza bruta (John)**

```Python
/JohnTheRipper/run/ssh2john.py id_rsa > forjohn.txt
/JohnTheRipper/run/john forjohn.txt --wordlist=/dir/wordlist.txt
```

**ssh-passwd-user fuerza bruta (Hydra)**

```Python
hydra -l 'user' -P /dir/wordlist ssh://IP 
```

#### Python
**Upgrade Reverse Shell**
```Python
python3 -c "import pty;pty.spawn('/bin/bash')"
```
**Simple Web Server**
```Python
python2 -m SimpleHTTPServer 4567
```
#### Busqueda de archivos
```Python
find / -user UsuarioQueTieneElArchivo -group grupoQuePuedeLeer -size BITSc (recordar el c)
```

```Python
find . -type f (para colocar archivos) -readable ! -executable -size BITSc
```

#### Binaries

**Recordar jugar con las SUID para escalar privilegios con ayuda de GTFObins**

```Python
find / perm -u=s -type f 2>/dev/null
```
```Python
find / -user root -perm -4000 -print 2>/dev/null
```
```Python
find / -user root -perm -4000 -exec ls -ldb {} \;
```
#### Stego
```Python
steghide extract -sf filename.txt
```
```Python
binwalk --dd '.*' flag.jpeg
```
```Python
hexdump -C flag.jpeg | grep S
```
```Python
for i in $(ls | \grep jpg); do exiftool $i && echo -e '\n--------------------------------------\n'; done
```
#### Others
**Another way to read a file**
**read a single file**
```Python
echo < archive.txt
while read line; do echo $line; done < archivo.txt
```
```Python
grep . archivo.txt
```
**read all files**
```Python
grep -R .
```
**Read the History Files**
```Python
cat ~/.*history | less
```
## Windows

**smb and rpc vuln scan in nmap**
```Python
nmap -v -script smb-vuln* -p 139,445 10.10.10.4
```

#### Linux

> [GTFOBins](https://gtfobins.github.io/)

> [ReverseShellsPM](http://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet)

> [escapar de shells restringidas](https://www.hackplayers.com/2018/05/tecnicas-para-escapar-de-restricted--shells.html)

> [Basic Linux Privilege Escalation](https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/)

>> [LinuxCheatSheets](https://gist.github.com/cocolote/e590d8dd828f7f06645b8600535ad53c)

## Herramientas
> [PsPy](https://github.com/DominicBreuker/pspy) 

> [LinEnum](https://github.com/rebootuser/LinEnum/)

> [PsPy64](https://f4d3.io/assets/downloads/linux/pspy64s) (grax f4d3 :D)

> []()

#### USM

> [Malla-Interactiva-USM](https://mallas.labcomp.cl/?m=TEL)

> [Lab-Redes](http://www2.elo.utfsm.cl/~tel241/20102s/)

#### Other

> [ExploitDB](https://www.exploit-db.com/)

> [Campo de Marte](https://www.campodemarte.cl/)

> [CTFtime](https://ctftime.org/)

> [Escritura Exploits (Español)](https://fundacion-sadosky.github.io/guia-escritura-exploits/)