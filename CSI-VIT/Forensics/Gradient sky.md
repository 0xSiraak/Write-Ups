# Gradient sky.md
La description de ce challenge ne donnait pas plus d'indice que ça hormis le fait que c'était une technique simple de stéganographie.
J'ai d'abord essayé de regarder l'image et de changer certaines choses pour voir si un flag resortait mais rien, je suis donc passé à une autre solution qui a marché :
```
Royaume-De-Ryuh:Downloads p1r4t3$ strings sky.jpg | grep "csictf"
csictf{j0ker_w4snt_happy}
```

Le flag de ce challenge était donc `csictf{j0ker_w4snt_happy}`
