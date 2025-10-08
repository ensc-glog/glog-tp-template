# Travaux pratiques de génie logiciel

## Cheat Sheet

### Dotnet

- Vérifier la version de .Net : `dotnet --version`
- Créer une application console : `dotnet new console -o <nom du projet>`
- Créer un service web : `dotnet new webapi -o <nom du projet>`
- Créer un projet de test : `dotnet new mstest -n <nom du projet>.UnitTests`
- Créer une référence depuis un projet vers un autre : `dotnet add <projet 1>.csproj reference <projet 2>.csproj`
- Créer un fichier `.gitignore` par défaut : `dotnet new gitignore`
- Ajouter un paquet à un projet : `dotnet add package <nom du paquet>`
- Pour gérer les problèmes de certificat :
```
dotnet dev-certs https --clean
dotnet dev-certs https --trust
```

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

- Installer les outils d'interface de ligne de commande (CLI) : `dotnet tool install --global dotnet-ef`
- Vérifier l'installation : `dotnet ef`
- Ajouter Entity Framework (avec SQLite) à un projet :
```
dotnet add package Microsoft.EntityFrameworkCore.Design
dotnet add package Microsoft.EntityFrameworkCore.Sqlite
```
- Ajouter une migration suite à évolution du modèle : `dotnet ef migrations add <message de migration>`
- Créer ou mettre à jour la base de données : `dotnet ef database update`

#### Exemple de fichier Context

```csharp
using Microsoft.EntityFrameworkCore;

public class TodoContext : DbContext
{
  private const string DbPath = "data.sqlite";

  // Mettre à jour cette section en fonction du projet (Models/)
  public DbSet<Todo> Todos { get; set; } = null!;
  public DbSet<List> Lists { get; set; } = null!;
  public DbSet<User> Users { get; set; } = null!;

  protected override void OnConfiguring(DbContextOptionsBuilder options)
  {
    options.UseSqlite($"Data Source={DbPath}");
  }
}
```
