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
