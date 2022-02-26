# Github Action pour compiler puis héberger sur une github page un .Rmd

1. Créer les fichiers `tutorials\exo.Rmd` et`tutorials\tuto.Rmd`. 

2. Créer le fichier [`.github\workflows\render-markdown.yaml`](.github\workflows\render-markdown.yaml)

*Remarque : il est possible d'initialiser un .yaml avec la commande `usethis::use_github_action("render-rmarkdown.yaml")` sur R.*

3. Faire un commit push

*Remarque : Il est nécessaire de générer un Personal access token qui a l'autorisation `workflows` et pas uniquement `repo`. *

4. Paramétrer l'URL de la github page du repertoire : *Settings > Pages > Source Branch : gh-pages / (root) Save*. 


C'est bon, les pages sont bien disponibles [ici](https://antuki.github.io/tests_github_actions/tuto.html) et [là](https://antuki.github.io/tests_github_actions/exi.html).

*Source : https://tgerke.github.io/github-actions-with-r/ et https://github.com/InseeFrLab/lockdown-maps-R*

