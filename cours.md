# 🚀 Cours Complet HTML/CSS & Sass (SCSS)

Bienvenue dans ce cours complet dédié à **Sass** (Syntactically Awesome Style Sheets), le préprocesseur CSS le plus populaire. Ce guide vous expliquera comment écrire du CSS plus propre, modulaire et maintenable.

---

## 📚 Table des matières
1. [Introduction à Sass](#1-introduction-à-sass)
2. [Sass vs SCSS](#2-sass-vs-scss)
3. [Installation & Configuration](#3-installation--configuration)
4. [Les Fonctionnalités Clés](#4-les-fonctionnalités-clés)
   - [Variables & Types de données](#variables--types-de-données)
   - [Nesting (Imbrication)](#nesting-imbrication)
   - [Partials & Modules (@use et @forward)](#partials--modules-use-et-forward)
   - [Mixins & Includes](#mixins--includes)
   - [Functions & Control Directives](#functions--control-directives)
5. [Architecture SASS (La méthode 7-1)](#5-architecture-sass-la-méthode-7-1)
6. [Exercice Pratique](#6-exercice-pratique)

---

## 1. Introduction à Sass
Sass est un **préprocesseur CSS**. Il vous permet de réutiliser du code, de créer des variables, d'imbriquer des règles CSS et d'écrire des fonctions logicisées. Le navigateur ne lisant pas directement le Sass, il doit être **compilé** en CSS standard.

---

## 2. Sass vs SCSS
Il existe deux syntaxes :
* **SCSS (Sassy CSS)** : Utilise la syntaxe `.scss`. C'est une surcouche de CSS avec des accolades `{}` et des points-virgules `;`. **C'est la syntaxe recommandée et la plus utilisée.**
* **Sass (Indented Syntax)** : Utilise l'extension `.sass`. Elle se base sur l'indentation et supprime les accolades et points-virgules.

---

## 3. Installation & Configuration

Vous pouvez installer Sass globalement via Node.js :

```bash
npm install -g sass
```

Pour compiler votre fichier SCSS en CSS en temps réel :

```bash
sass --watch src/scss/style.scss dist/css/style.css
```

---

## 4. Les Fonctionnalités Clés

### Variables & Types de données
Les variables commencent par le symbole `$`.

```scss
// Variables
$primary-color: #3498db;
$font-stack: 'Helvetica', sans-serif;
$spacing-base: 16px;

body {
  font-family: $font-stack;
  background-color: $primary-color;
  padding: $spacing-base;
}
```

### Nesting (Imbrication)
Imbriquez vos sélecteurs CSS pour reproduire la structure HTML. Utilisez `&` pour faire référence au sélecteur parent.

```scss
.card {
  background-color: #fff;
  padding: 20px;

  .card-title {
    font-size: 1.5rem;
    color: #333;
  }

  &:hover {
    box-shadow: 0 4px 8px rgba(0,0,0,0.1);
  }
}
```

### Partials & Modules (@use et @forward)
Pour découper votre code, créez des fichiers "partials" qui commencent par un tiret bas `_` (ex: `_variables.scss`). Sass ne les compilera pas séparément.

Importez-les avec la directive `@use` :

```scss
// _variables.scss
$theme-color: #2ecc71;

// style.scss
@use 'variables';

button {
  background-color: variables.$theme-color;
}
```

### Mixins & Includes
Les mixins permettent de regrouper des déclarations CSS réutilisables, avec ou sans paramètres.

```scss
@mixin flex-center($direction: row) {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: $direction;
}

.header {
  @include flex-center(row);
}

.hero-section {
  @include flex-center(column);
}
```

### Functions & Control Directives
Vous pouvez créer vos propres fonctions et utiliser des structures conditionnelles (`@if`, `@else`) ou des boucles (`@for`, `@each`).

```scss
@function rem($pixels) {
  @return ($pixels / 16px) * 1rem;
}

.container {
  width: rem(320px); // Résultat: 20rem
}

// Boucle @each
$theme-colors: (
  "success": #27ae60,
  "warning": #f39c12,
  "danger": #e74c3c
);

@each $state, $color in $theme-colors {
  .btn-#{$state} {
    background-color: $color;
  }
}
```

---

## 5. Architecture SASS (La méthode 7-1)
Pour les projets d'envergure, organisez votre code selon la convention 7-1 (7 dossiers, 1 fichier principal) :

```text
sass/
|-- abstracts/     # Variables, mixins, fonctions
|-- base/          # Reset, typographie globale
|-- components/    # Boutons, cartes, modales
|-- layout/        # Header, footer, grid, navigation
|-- pages/         # Styles spécifiques aux pages
|-- themes/        # Thèmes (mode sombre/clair)
|-- vendors/       # Librairies externes (Bootstrap, etc.)
`-- main.scss      # Fichier principal qui importe tout
```

---

## 6. Exercice Pratique
1. Créez un projet avec la structure de dossiers ci-dessus.
2. Définissez une palette de couleurs dans `abstracts/_variables.scss`.
3. Créez un mixin pour la gestion des media queries responsive dans `abstracts/_mixins.scss`.
4. Compilez votre code et vérifiez la sortie CSS.
