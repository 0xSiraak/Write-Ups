# Petite frappe 1

<img src="https://media.discordapp.net/attachments/707349064919810129/707613434065190943/unknown.png?width=684&height=1132" height="600" width="500"></img>

Pour ce challenge les données qui nous sont fournis sont la capture d'un clavier émise faites par un key logger ou enregistreur de frappe en français.
Voici un exemple de ce qu'on retrouve dans ce fichier texte :
````
Event: time 1584656705.424839, -------------- SYN_REPORT ------------
Event: time 1584656706.404214, type 4 (EV_MSC), code 4 (MSC_SCAN), value 16
Event: time 1584656706.404214, type 1 (EV_KEY), code 22 (KEY_U), value 1
Event: time 1584656706.404214, -------------- SYN_REPORT ------------
Event: time 1584656706.508350, type 4 (EV_MSC), code 4 (MSC_SCAN), value 16
Event: time 1584656706.508350, type 1 (EV_KEY), code 22 (KEY_U), value 0
Event: time 1584656706.508350, -------------- SYN_REPORT ------------
Event: time 1584656706.674591, type 4 (EV_MSC), code 4 (MSC_SCAN), value 31
Event: time 1584656706.674591, type 1 (EV_KEY), code 49 (KEY_N), value 1
Event: time 1584656706.674591, -------------- SYN_REPORT ------------
Event: time 1584656706.774463, type 4 (EV_MSC), code 4 (MSC_SCAN), value 31
Event: time 1584656706.774463, type 1 (EV_KEY), code 49 (KEY_N), value 0
Event: time 1584656706.774463, -------------- SYN_REPORT ------------
Event: time 1584656706.926206, type 4 (EV_MSC), code 4 (MSC_SCAN), value 12
Event: time 1584656706.926206, type 1 (EV_KEY), code 18 (KEY_E), value 1
Event: time 1584656706.926206, -------------- SYN_REPORT ------------
Event: time 1584656707.023728, type 4 (EV_MSC), code 4 (MSC_SCAN), value 12
Event: time 1584656707.023728, type 1 (EV_KEY), code 18 (KEY_E), value 0
````

Avec du recul on se rend très vite compte que le déterminant `une` apparaît, or si on prend lettre par lettre cela donnerait UUNNEE. Après quelques recherches sur le net on s'apperçoit que lorsqu'il y'a `value 1` c'est que la touche est enfoncé et `value 0` la touche est relâché. En conclusion cela donne bien `UNE` et pas `UUNNEE`.
Bref je vous épargne les étapes suivantes mais ce qui nous donne comme résultat : `UNEGENTILLEINTRODUCTION`, rajoutez-y à ça le `FCSC{}` et vous voilà en possesion d'un nouveau flag.
