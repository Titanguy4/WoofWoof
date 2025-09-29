# WoofWoof

![alt text](logo.png)

**WoofWoof** est une application web moderne dédiée aux amoureux du woofing. Ce projet propose une application mobile permettant aux utilisateurs de poster des annonces, trouver des propositions de woofing facilement et partager et interagir autour de l'univers du woofing.

## Table des matières

- [À propos du projet](#à-propos-du-projet)
- [Architecture](#architecture)
- [Installation](#installation)
- [Structure du projet](#structure-du-projet)
- [Mise à jour automatique](#mise-à-jour-automatique)
- [Crédits](#crédits)
- [Licence](#licence)

## À propos du projet

WoofWoof est une application full-stack composée de :

- **Frontend** : Application mobile basé sur React Native avec Respo
- **Backend** : API structurée en microservices à l'aide du framework Spring Boot

Ce projet a été développé dans le cadre du module IWA (Ingénierie Web Avancée) en IG5 à Polytech Montpellier.

## Architecture

Le projet utilise une architecture modulaire avec des **submodules Git** pour séparer le frontend et le backend, et ainsi faciliter le déploiement de l'API.

## Installation

### Cloner le projet

Cloner le repository principal avec les submodules

```bash
git clone --recurse-submodules https://github.com/mon-org/mon-repo.git
```

Puis si vous voulez push une modification dans un submodule, il ne faut pas oublier d'aller sur une branche

```bash
git branch -a
git checkout main # par exemple
```

## Structure du projet

### Submodules

Le projet utilise des submodules Git pour organiser le code :

- **`WoofWoof-backend/`** : Submodule pointant vers [WoofWoof-backend](https://github.com/Titanguy4/WoofWoof-backend)
- **`WoofWoof-frontend/`** : Submodule pointant vers [WoofWoof-frontend](https://github.com/Titanguy4/WoofWoof-frontend)

Nous avons décidé cette organisation à la place d'un monorepo, car plus facile pour déployer notre API.

## Mettre à jour les submodules

### 🔄 Mise à jour automatique

Le projet intègre des **GitHub Action** qui mettent automatiquement à jour les submodules :

- **Fichier** : `.github/workflows/update-submodules.yml`
- **Déclenchement** : Via `repository_dispatch` depuis les repos frontend/backend
- **Action** : Met à jour les submodules vers la dernière version et commit les changements

### Fonctionnement

1. Lorsqu'un commit est poussé sur `main` dans le frontend ou backend
2. Une webhook déclenche l'action dans le repo principal
3. Les submodules sont automatiquement mis à jour
4. Un commit automatique est créé : `"chore: update submodules to latest"`

## Crédits

Ce projet a été développé par :

- **Lisandre Begon** - @lisandre-begon
- **Yanis Baroudi** - @ledzsucrey213
- **Hugo Tanguy** - @Titanguy4

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus de détails.
