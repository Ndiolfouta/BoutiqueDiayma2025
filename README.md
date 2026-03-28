# Boutique Diayma 2025

## Description
Application web de boutique en ligne développée en ASP.NET Core MVC.

## Lien GitHub original
https://github.com/devehod/BoutiqueDiayma2025

---

## Q2 — Projets de la solution
La solution **Diayma.sln** contient un seul projet :
- **P2FixAnAppDotNetCode** : Application web ASP.NET Core MVC (Boutique Diayma)

---

## Q3 — Version SDK .NET utilisée
- Version originale du projet : **netcoreapp2.0**
- Version utilisée pour l'exécution : **net10.0** (SDK 10.0.201)

---

## Q6 — Bugs trouvés et corrigés

### Bug 1 — Version SDK incompatible
- **Fichier :** `Diayma.csproj`
- **Problème :** Le projet ciblait `netcoreapp2.0` qui n'est plus supporté. L'application ne pouvait pas démarrer.
- **Correction :** Changé `<TargetFramework>netcoreapp2.0</TargetFramework>` en `<TargetFramework>net10.0</TargetFramework>`

### Bug 2 — Endpoint Routing incompatible avec UseMvc
- **Fichier :** `Startup.cs`
- **Problème :** `UseMvc()` n'est pas compatible avec le routing moderne de .NET 10. L'application crashait au démarrage avec l'erreur `InvalidOperationException`.
- **Correction :** 
  - Ajouté `options.EnableEndpointRouting = false` dans `AddMvc()`
  - Remplacé `IHostingEnvironment` par `IWebHostEnvironment`

---

## Q8 — Namespaces, classes et méthodes visités

### Mode de débogage choisi : Pas à pas principal (F10)
Ce mode a été choisi car il permet d'observer le flux général de l'application
en avançant ligne par ligne sans entrer dans chaque méthode interne,
ce qui est approprié pour suivre l'enchaînement des appels jusqu'à
l'affichage des produits.

### Ordre d'exécution avant l'affichage des produits :

#### 1. Namespace : `P2FixAnAppDotNetCode`
- **Classe :** `Startup`
- **Méthode :** `Configure()`
- **Rôle :** Configure le pipeline HTTP et le routing de l'application

#### 2. Namespace : `P2FixAnAppDotNetCode.Controllers`
- **Classe :** `ProductController`
- **Méthode :** `Index()`
- **Rôle :** Reçoit la requête HTTP GET sur `/` et demande la liste des produits

#### 3. Namespace : `P2FixAnAppDotNetCode.Models.Services`
- **Classe :** `ProductService`
- **Méthode :** `GetAllProducts()`
- **Rôle :** Récupère les produits depuis le repository et les prépare pour la vue

#### 4. Namespace : `P2FixAnAppDotNetCode.Models.Repositories`
- **Classe :** `ProductRepository`
- **Méthode :** `GetAllProducts()`
- **Rôle :** Retourne la liste complète des produits disponibles

#### 5. Namespace : `P2FixAnAppDotNetCode.Components`
- **Classe :** `CartSummaryViewComponent`
- **Méthode :** `Invoke()`
- **Rôle :** Affiche le résumé du panier dans le header de la page

---

## Q9 — Déploiement Windows
L'application a été déployée sous forme d'exécutable Windows autonome.
- **Commande utilisée :**
```bash
dotnet publish -c Release -r win-x64 --self-contained true
```
- **Lien de téléchargement :** *(à compléter avec le lien Google Drive ou OneDrive)*
