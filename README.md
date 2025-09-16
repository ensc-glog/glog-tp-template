# Travaux pratique de génie Logiciel

## Cheat Sheet

### Dotnet

- Créer une application console : `dotnet new console -o <nom du projet>`
- Créer un service web : `dotnet new webapi -o <nom du projet>`
- Créer un projet de test : `dotnet new mstest -n <nom du projet>.UnitTests`
- Créer une référence depuis un projet vers un autre : `dotnet add <projet 1>.csproj reference <projet 2>.csproj`
- Créer un fichier `.gitignore` par défaut : `dotnet new gitignore`

### Git

- Configurer git sur la machine :
```
git config --global user.name <Prénom Nom>
git config --global user.email <email@ensc.fr>
```
- Cloner un dépôt : `git clone <adresse du dépôt>`
- Ajouter tous les fichiers à l’index : `git add .`
- Archiver une modification : `git commit -m <message de commit>`
- Pousser vers le dépôt distant : `git push`
- Récupérer les modification distantes :
  - mettre à jour l’espace de travail : `git pull`
  - ne pas modifier l’espace de travail : `git fetch`
- Regarder le statut du dépôt local : `git status`

### C#

- Afficher une ligne console : `Console.WriteLine("Enter username:");`
- Lire une ligne console : `string userName = Console.ReadLine();`
- Effacer la console : `Console.Clear(); `

### Linq

### Entity Framework
