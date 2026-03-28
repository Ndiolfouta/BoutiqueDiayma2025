# Boutique Diayma 2025

## Description
Application web de boutique en ligne développée en ASP.NET Core MVC.

## Lien GitHub original
https://github.com/devehod/BoutiqueDiayma2025

---

## Q2 — Projets de la solution
La solution Diayma.sln contient un seul projet :
- P2FixAnAppDotNetCode : Application web ASP.NET Core MVC (Boutique Diayma)

---

## Q3 — Version SDK .NET utilisée
- Version originale du projet : netcoreapp2.0
- Version utilisée pour l'exécution : net10.0 (SDK 10.0.201)

---

## Q6 — Bugs trouvés et corrigés
Les Bugs: Version SDK incompatible et Endpoint Routing incompatible avec UseMvc

### Bug 1 — Version SDK incompatible
- Fichier : Diayma.csproj
- Problème : Le projet ciblait netcoreapp2.0 qui n'est plus supporté.
- Correction : Changé en net10.0

### Bug 2 — Endpoint Routing incompatible avec UseMvc
- Fichier : Startup.cs
- Problème : UseMvc() n'est pas compatible avec le routing moderne de .NET 10.
- Correction : Ajouté EnableEndpointRouting = false et remplacé IHostingEnvironment par IWebHostEnvironment

---

## Q8 — Namespaces, classes et méthodes visités avant l'affichage des produits

### Mode choisi : Pas à pas principal (F10)
Ce mode permet d'avancer ligne par ligne dans le code principal
sans entrer dans les détails des méthodes appelées.

### Namespaces, classes et méthodes visités :

1. Namespace : P2FixAnAppDotNetCode
   - Classe : Startup
   - Méthode : Configure()

2. Namespace : P2FixAnAppDotNetCode.Controllers
   - Classe : ProductController
   - Méthode : Index()

3. Namespace : P2FixAnAppDotNetCode.Models.Services
   - Classe : ProductService
   - Méthode : GetAllProducts()

4. Namespace : P2FixAnAppDotNetCode.Models.Repositories
   - Classe : ProductRepository
   - Méthode : GetAllProducts()

5. Namespace : P2FixAnAppDotNetCode.Components
   - Classe : CartSummaryViewComponent
   - Méthode : Invoke()

---

## Q9 — Déploiement Windows
Commande utilisée :
dotnet publish -c Release -r win-x64 --self-contained true

---

## Q10 — Lien exécutable Windows
[Télécharger l'exécutable](https://drive.google.com/file/d/1VJp_CIvwhYP4B3C59LQqsfytuEWsg6VC/view?usp=sharing)
