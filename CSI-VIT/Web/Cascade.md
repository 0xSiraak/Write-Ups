# Cascade
Le challenge Cascade était assez simple en lisant l'énoncé qui était : "Flag in CSS.", en voyant ça j'ai donc directement affiché le code source de la page ce qui m'a donné :
`<link rel="stylesheet" href="/static/style.css">`.

Suite à cette trouvaille je me suis rendu dans le fichier et j'y ai trouvé ceci :
```
body {
    background-color: purple;
    text-align: center;
    display: flex;
    align-items: center;
    flex-direction: column;
}

h1, div, a {
    /* csictf{w3lc0me_t0_csictf} */
    color: white;
    font-size: 3rem;
}
```

Le flag de ce challenge était donc `csictf{w3lc0me_t0_csictf}`
