# package
## Chercher dans quel paquet se trouve une commande XXX
Le nombre de temps que j'ai perdu à trouver quel paquet installer pour avoir cette fichue commande XXX est colossal. Ca vallait bien un premier article sur les paquets...
```sh
user@host:~$ for p in $( apt-cache pkgnames ) ; do echo ">> $p" ; apt-cache show "$p" | grep XXX ; done > res
```
Pour visualiser en direct l'avancement :
```sh
user@host:~$ watch -n 1 grep -B1 XXX res
```
