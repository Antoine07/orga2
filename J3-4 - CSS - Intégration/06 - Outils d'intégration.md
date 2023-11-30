# Outils d'intégration

Il existe des outils permettant d'être plus efficace dans le développement d'un site web.

Ces outils fonctionnent sur l'environnement **Node.js**, et sont installés via **NPM**.

## NPM

NPM est le gestionnaire de packages par défaut de Node.js

Il se compose de 2 choses :

#### 1. Une **base de données en ligne** de modules publics et privés payants, appelée le _registre NPM_

À ce jour, il existe un peu plus de 1.9 Millions de modules disponibles publiquement dans le registre NPM.

Le site officiel propose un moteur de recherche afin d'explorer tous les modules disponibles : https://npmjs.org

La communauté Node.js dans le monde (y compris vous) peut ainsi créer des packages et les publier dans cette base pour qu'ils soient utilisables par tous.

#### 2. Une interface client de ligne de commande (CLI), appelée npm et installée par défaut avec la commande node

Ce CLI permet d'installer, désinstaller et mettre à jour des modules (appelés aussi des "packages" ou "dépendances") présents dans la base de registre NPM, pour une application Node.js.

## Démarrer un projet

Tout projet fonctionnant sous l'écosystème Node.js doit contenir un fichier manifeste : le fichier `package.json`

Ce fichier contient toutes les informations propres à un projet fonctionnant sur l'environnement Node.js, à savoir :

- Son nom, sa version, sa description, son/ses auteur(s), le type de licence open-source
- Les _scripts_ pouvant être lancés dans le terminal
- Les packages utilisés (appelés aussi les **dépendances** du projet)

Pour créer ce fichier, on peut le faire à la main ou **s'aider d'un utilitaire**.

Pour lancer l'utilitaire, on tape la commande suivante :

```bash
npm init
```

Un petit questionnaire va alors démarrer pour nous aider à créer le fichier manifeste `package.json`

La structure basique d'un tel fichier ressemble à ceci :

```js
{
  "name": "my-project",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```

Les différentes clés ont chacune une utilité descriptive ou fonctionnelle vis-à-vis du projet.

Voir la documentation sur le fichier "package.json" : https://docs.npmjs.com/files/package.json

## Les scripts NPM

La clé `scripts` représente un ensemble de sous-clés contenants des commandes de script exécutables à différents moments du cycle de vie du projet.

Il peut s'agir de commandes pour lancer un serveur de développement, compiler une application, déployer un application, …

On peut complètement personnaliser ses commandes, par exemple :

```js
{
  // …
  "scripts": {
    "dev": "concurrently \"http-server --port=1337\" \"sass --watch\"",
    "build": "sass --style compressed index.scss /build/app.min.css"
  }
}
```

Les commandes peuvent ensuite être invoquées dans un terminal grâce à `npm run NOM_DU_SCRIPT` :

```bash
npm run dev

# invoque la commande : concurrently "http-server --port=1337" "sass --watch"
```

```bash
npm run build

# invoque la commande : sass --style compressed index.scss /build/app.min.css
```

