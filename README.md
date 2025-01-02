# Play JZS

Collection de jeux interactifs hébergée sur play.jzs.fr.

## Structure du projet

Ce projet utilise des Git submodules pour gérer les différents jeux. Chaque jeu est un dépôt Git indépendant, ajouté comme submodule à la racine du projet.

```
play.jzs.fr/
├── index.html     # Page d'accueil listant tous les jeux
├── README.md      # Ce fichier
├── game1/         # Premier jeu (submodule)
├── game2/         # Deuxième jeu (submodule)
└── ...
```

## Ajouter un nouveau jeu

1. Créez un nouveau dépôt pour votre jeu sur GitHub
2. Ajoutez-le comme submodule à ce projet :
   ```bash
   git submodule add https://github.com/username/repo-name.git nom-du-dossier
   ```
3. Mettez à jour index.html pour ajouter une carte pour le nouveau jeu
4. Committez les changements :
   ```bash
   git add .
   git commit -m "Ajout du jeu : nom-du-jeu"
   git push
   ```

## Mettre à jour les jeux

Pour mettre à jour tous les submodules :
```bash
git submodule update --remote
```

Pour mettre à jour un jeu spécifique :
```bash
cd nom-du-jeu
git pull origin main
cd ..
git add nom-du-jeu
git commit -m "Mise à jour du jeu : nom-du-jeu"
git push
```
