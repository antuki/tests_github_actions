# tests_github_actions

# Apprendre à faire un github action pour compiler puis héberger un Rmd

1. Générer un Personal access token qui a l'autorisation `workflows` et pas uniquement `repo`. 

2. Créer le fichier `tutorials\tutorial1.Rmd`. 

3. Initialiser le CI. Pour cela, taper la commande R suivante : 

```
usethis::use_github_action("render-rmarkdown.yaml")
```

=> Le fichier `.github/worklows/render-rmarkdown.yaml`  est initialisé

3. 


*Source : https://tgerke.github.io/github-actions-with-r/*

