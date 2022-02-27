# Github Action pour compiler puis héberger sur une github page un .Rmd

1. Créer les fichiers `tutorials\index.Rmd` (page d'accueil), `tutorials\exo.Rmd` et`tutorials\tuto.Rmd`. 

2. Créer le fichier [`.github\workflows\render-markdown.yaml`](.github\workflows\render-markdown.yaml)

*Remarque 1 : il est possible d'initialiser un .yaml avec la commande `usethis::use_github_action("render-rmarkdown.yaml")` sur R.*

*Remarque 2 : les lignes 28 à 32 ne sont pas (encore) généralisées à tous les répertoires. A ce stade, il faut remplacer par les informations de votre futur répertoire "à la main" : les packages utiles à installer + le lien vers votre répertoire au lieu de `antuki\tests_github_action` pour copier coller les html déjà existants dans la branche `gh-pages` + le nom du répertoire où les Rmd sont stockés, ici `tutorials`*

```
          Rscript -e 'install.packages(c("remotes","rmarkdown","prettydoc"))'
          Rscript -e "remotes::install_github('koncina/unilur')"
          Rscript -e "download.file('https://github.com/antuki/tests_github_actions/archive/refs/heads/gh-pages.zip',
              destfile = 'gh-pages.zip')"
          Rscript -e "unzip('gh-pages.zip', overwrite = FALSE, exdir='tutorials/', junkpaths = TRUE)"
```
*idem pour la ligne 42* :

```
          mv tutorials/*.html build
```


3. Faire un commit push

*Remarque : Il est nécessaire de générer un Personal access token qui a l'autorisation `workflows` et pas uniquement `repo`. *

4. Paramétrer l'URL de la github page du repertoire : *Settings > Pages > Source Branch : gh-pages / (root) Save*. 


C'est bon, les pages sont bien disponibles [par ici](https://antuki.github.io/tests_github_actions), [par là](https://antuki.github.io/tests_github_actions/tuto.html) et [par là-bas](https://antuki.github.io/tests_github_actions/exo.html).

*Source : https://tgerke.github.io/github-actions-with-r/ et https://github.com/InseeFrLab/lockdown-maps-R*

