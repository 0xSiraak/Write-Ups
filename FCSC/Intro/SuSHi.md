# SuSHi

Un challenge également assez simple comme les autres qui étaient présent dans l'Intro.
Afin de commencer convenablement ce challenge on a quelques données qui nous sont fournies :
```
Adresse : challenges2.france-cybersecurity-challenge.fr
Port : 6000
Utilisateur : ctf
Mot de passe : ctf
```
Grâce à ça on connaît donc l'hôte, le port, l'utilisateur et le mot de passe de la machine à laquelle on doit se connecter (logique à vrai dire). On se connecte donc au ssh en utilisant la commande `ssh -p 6000 ctf@challenges2.france-cybersecurity-challenge.fr`.

Une fois connecté on observe ceci :
```
 __    __            _                 __           _     _   ___ 
/ / /\ \ \__ _ _ __ | |_      __ _    / _\_   _ ___| |__ (_) / _ \
\ \/  \/ / _` | '_ \| __|    / _` |   \ \| | | / __| '_ \| | \// /
 \  /\  / (_| | | | | |_    | (_| |   _\ \ |_| \__ \ | | | |   \/ 
  \/  \/ \__,_|_| |_|\__|    \__,_|   \__/\__,_|___/_| |_|_|   () 
ctf@SuSHi:~$ 

```
Dans un premier temps j'essaie donc d'effectuer la commande `ls` afin d'afficher les fichiers présents sur la machine mais rien de concret, je décide donc d'utiliser la commande `ls -la`.
```
total 24
drwxr-xr-x 1 ctf-admin ctf 4096 Apr 25 10:39 .
drwxr-xr-x 1 ctf-admin ctf 4096 Apr 25 10:38 ..
-rw-r--r-- 1 ctf-admin ctf  220 May 15  2017 .bash_logout
-rw-r--r-- 1 ctf-admin ctf 3526 May 15  2017 .bashrc
-r--r--r-- 1 ctf-admin ctf   71 Apr 25 10:38 .flag
-rw-r--r-- 1 ctf-admin ctf  675 May 15  2017 .profile
```
Plus qu'à lire le fichier `.flag` à l'aide de la commande `cat` en faisant `cat .flag`
```
ctf@SuSHi:~$ cat .flag 
FCSC{ca10e42620c4e3be1b9d63eb31c9e8ffe60ea788d3f4a8ae4abeac3dccdf5b21}
```
Voilà un nouveau flag de prit donc un nouveau challenge de validé !
