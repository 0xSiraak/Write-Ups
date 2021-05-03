# (Intro) Push It to the Limit - 20 points

![image](https://siraak.please-fuck.me/P07YLl.png)

Un challenge rapide et simple, en arrivant sur la page on y trouve un login avec dans le code source la requête SQL qui est faite.

![image](https://siraak.please-fuck.me/lp3dvi.png)

Après avoir mis en username `"` et en password `a`, j'ai bien eu le retour d'une erreur SQL `Erreur : near "a": syntax error`.
On essaye donc de nouveau en remplaçant l'username par `admin" --` ce qui nous affiche le flag dans un jolie encadré vert.

# Flag
FCSC{5012fb37d7886deaa5c4e209cf683286}
