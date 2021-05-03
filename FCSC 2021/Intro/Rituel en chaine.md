# (Intro) Rituel en chaine - 20 points

![image](https://siraak.please-fuck.me/fjy6dD.png)

On dispose d'un fichier disque.img, avant de le mount j'ai préféré faire un `strings * | grep "FCSC"` ce qui m'a retourné le flag aisément
```
strings: Warning: '_disque.img.extracted' is a directory
C:\Users\Admin\Desktop\FCSC\bonuspoints
; File Name   : C:\Users\Admin\Desktop\FCSC\bonuspoints
string = "FCSC{"
FCSC{6b8aa82937ec0ff5a3eaffa74b3b2de2e83c6a94eef6d96b59b50f65e8e35fa9}
VFCSCr$q+
C:\Users\Admin\Desktop\FCSC\guessy
; File Name   : C:\Users\Admin\Desktop\FCSC\guessy
```

Il y avait également un autre moyen de le faire en extrayant le `_disque.img.extracted` ce qui nous donnaît ensuite un fichier `0.ext` ou était contenu le flag.

# Flag
FCSC{6b8aa82937ec0ff5a3eaffa74b3b2de2e83c6a94eef6d96b59b50f65e8e35fa9
