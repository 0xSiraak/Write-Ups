# (Intro) Bonus Points - 20 points

![image](https://siraak.please-fuck.me/V6RIKB.png)

En commençant ce challenge j'avoue que j'étais un peu perdu car j'ai commencé d'abord par essayé d'additionner ou multiplier plusieurs valeurs entres elles et je voyais que ça marchait pas. J'ai donc décidé de chercher sur internet et je suis tombé sur ce lien : `https://stackoverflow.com/questions/16056758/c-c-unsigned-integer-overflow#:~:text=A%20computation%20involving%20unsigned%20operands,represented%20by%20the%20resulting%20type.`, après lecture je me suis donc rendu compte qu'il suffisait d'additionner un nombre négatif.
Voici un script qui peut vous aider à résoudre ce challenge 

```py
import pwn

a = pwn.remote("challenges2.france-cybersecurity-challenge.fr", "4001")
a.sendline("-100");
a.interactive()
```
