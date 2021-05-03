# (Intro) Dérèglement - 20 points

![image](https://siraak.please-fuck.me/66Zs49.png)

On trouve ici un fichier nommé `2021-fcsc-reglement_de_participation.docx`, étant donné que c'est un fichier je décide donc par de l'examiner d'abord avec un `strings`, ce qui n'a malheureusement rien donné.
Je suis donc partit sur l'utilisation de l'outil `binwalk`

![image](https://user-images.githubusercontent.com/55248135/116907789-580d0780-ac42-11eb-9a90-df9053954129.png)

On peut voir qu'à la base le fichier est donc compressé, je fais donc un `unzip 2021-fcsc-reglement_de_participation.docx` ce qui me retourne :

```
Archive:  2021-fcsc-reglement_de_participation.docx
  inflating: [Content_Types].xml
   creating: docProps/
  inflating: docProps/app.xml
  inflating: docProps/core.xml
   creating: _rels/
  inflating: _rels/.rels
   creating: word/
   creating: word/_rels/
  inflating: word/_rels/document.xml.rels
  inflating: word/document.xml
  inflating: word/styles.xml
  inflating: word/numbering.xml
  inflating: word/settings.xml
  inflating: word/fontTable.xml
   creating: word/media/
  inflating: word/media/image1.jpeg
  ```
  
  Je me rend dans le directory `word`, et je fais un `grep -R "FCSC"` ce qui va me permettre de recherche parmis les fichiers extraits le flag et bingo !
  
  ![image](https://user-images.githubusercontent.com/55248135/116908041-ba660800-ac42-11eb-8e78-314837f567d8.png)
  
  # Flag
  FCSC{9bc5a6d51022ac}
