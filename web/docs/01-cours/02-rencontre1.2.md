---
title: Introduction à CSS
description: Cours 1.2 - Introduction à CSS
---

# Introduction à CSS - Rencontre #2

## 📋 Table des matières

1. [Qu'est-ce que CSS ?](#-quest-ce-que-css)
2. [Syntaxe de CSS](#-syntaxe-de-css)
3. [Méthodes d'application du CSS](#-méthodes-dapplication-du-css)
4. [Les sélecteurs CSS](#-les-sélecteurs-css)
5. [Priorité des sélecteurs](#-priorité-des-sélecteurs)
6. [CSS externe](#-css-externe)
7. [Éléments de groupement](#-éléments-de-groupement)
8. [Éléments s��mantiques HTML5](#-éléments-sémantiques-html5)
9. [Styles de base - Couleurs](#-styles-de-base---couleurs)
10. [Styles de texte](#-styles-de-texte)
11. [Styles de police](#-styles-de-police)

---

## 🎨 Qu'est-ce que CSS ?

### Introduction à CSS

<!-- ![Logo CSS](../../static/img/1/logo-css.png) -->

**CSS** = **C**ascading **S**tyle **S**heet (Feuille de style en cascade)

---

### Définition

CSS permet de décrire **comment les éléments HTML doivent être affichés** :
- **Couleur** du texte et des arrière-plans
- **Taille** des éléments
- **Bordures** et contours
- **Position** des éléments
- **Polices** de caractères
- etc.

---

### Avantages du CSS

✅ **Économie de temps et de code**

Peut décrire l'affichage de plusieurs pages à la fois ! (Économie de temps et de code)

✅ **Séparation du contenu et du style**

Le HTML s'occupe de la structure, le CSS s'occupe de l'apparence.

✅ **Fonctionne avec des sélecteurs et des règles**

Les **sélecteurs** permettent de cibler les éléments HTML, et les **règles** définissent leur style.

---

### Exemple simple

Voici un petit morceau de CSS qui change le style de notre paragraphe :

```html
<p style="color:violet;">Petit paragraphe de couleur violette.</p>
```

<!-- ![Exemple CSS violet](../../static/img/1/exemple-css-violet.png) -->

**Rendu :**
```
Petit paragraphe de couleur violette.
```
(en violet)

`color:violet;` est un petit morceau de CSS qui change le style de notre paragraphe.

---

## 📝 Syntaxe de CSS

### Structure d'une règle CSS

Chaque modification appliquée à un élément est représentée par une **règle**.

Une règle est composée d'un **attribut** et d'une **valeur** :

```css
attribut: valeur;
```

**Quelques exemples :**

```css
color: blue;
border: solid black 3px;
text-decoration: none;
font-weight: bold;
```

### 📌 Points importants

✅ Deux points séparent l'**attribut** et sa **valeur**

✅ Un point-virgule conclut la règle

---

## 🔧 Méthodes d'application du CSS

Il existe **3 manières** d'appliquer une règle CSS :

1. **CSS Intraligne** (dans la balise ouvrante avec `style="..."`)
2. **CSS interne** (dans le `<head>` avec `<style>`)
3. **CSS externe** (fichier `.css` séparé)

---

### Manière #1 : CSS Intraligne

On glisse les règles CSS dans l'attribut **style** d'une balise ouvrante.

Comme pour tout attribut, les règles CSS devront être entourées de guillemets.

**Exemple :**

```html
<p style="color:red;">Paragraphe rouge.</p>
```

<!-- ![CSS Intraligne](../../static/img/1/css-intraligne.png) -->

**HTML complet :**

```html
<html>
    <!-- ... -->
    <body>
        <h1 style="font-weight:bold;color:blue;">Allo</h1>
    </body>
</html>
```

**Rendu :**
- Exemple
- Bonjour
- Allo

---

### Manière #2 : CSS interne

Pour comprendre cette deuxième méthode, nous devons d'abord étudier les **sélecteurs CSS**.

Un **sélecteur** permet d'indiquer à quel(s) élément(s) HTML des règles CSS doivent être appliquées.

Voici la syntaxe à respecter pour le CSS interne :

```css
sélecteur {
    attribut: valeur;
    attribut: valeur;
    attribut: valeur;
}
```

---

### CSS interne (Sélecteurs)

#### Type 1 de sélecteur : Sélecteur élément

Ce type de sélecteur correspond exactement au nom de l'élément HTML auquel le CSS sera appliqué.

**Pour appliquer un style** (un ensemble de règles CSS) à toutes les balises `<p>`, le sélecteur sera **p**.

**Pour appliquer un style** à toutes les balises `<h1>`, le sélecteur sera **h1**.

**Exemple :**

```css
p {
    color: blue;
}

h1 {
    font-size: large;
    font-weight: bold;
}
```

<!-- ![Sélecteur élément](../../static/img/1/selecteur-element.png) -->

Ce petit carré bleu est un échantillon de la couleur automatiquement généré par VS Code.

---

### Où insère-t-on le CSS interne avec les sélecteurs ?

Dans la balise `<style>`, dans une balise qu'on nomme `<style>` :

```html
<head>
    <meta charset="UTF-8">
    <title>Page d'exemple</title>
    <style>
        p {
            color: blue;
            font-size: large;
            font-weight: bold;
        }
    </style>
</head>

<body>
    <h1>Titre de la page</h1>
    <p>Paragraphe en bleu.</p>
</body>
```

<!-- ![CSS interne dans head](../../static/img/1/css-interne-head.png) -->

**Rendu :**
- Titre de la page
- Paragraphe en bleu.

---

## 🎯 Les sélecteurs CSS

Il existe plusieurs types de sélecteurs CSS. Voici les 3 principaux :

1. **Sélecteur élément** (p, h1, div, etc.)
2. **Sélecteur classe** (.nom_classe)
3. **Sélecteur id** (#nom_id)

---

### Type 2 de sélecteur : Sélecteur classe

Ce type de sélecteur peut avoir n'importe quel nom, mais il doit être appliqué aux éléments concernés grâce à l'attribut **class**.

**Exemple :**

```html
<p class="ma_classe">Paragraphe en violet.</p>
```

**Remarquez que ce sélecteur DOIT être précédé d'un point.** Cela dit, quand on précise le nom de la classe dans l'attribut **class**, on ne met pas de point.

On peut appliquer cette classe à autant d'éléments qu'on le souhaite !

```css
.ma_classe {
    color: rebeccapurple;
}
```

<!-- ![Sélecteur classe](../../static/img/1/selecteur-classe.png) -->

**Rendu :**

```
Titre de la page
Paragraphe en violet.
```

---

### Type 3 de sélecteur : Sélecteur id

Ce type de sélecteur peut avoir n'importe quel nom, mais il doit être appliqué à l'élément concerné grâce à l'attribut **id**.

**Exemple :**

```css
#mon_id {
    color: goldenrod;
}
```

```html
<p id="mon_id">Paragraphe en jaune.</p>
```

<!-- ![Sélecteur id](../../static/img/1/selecteur-id.png) -->

**Remarquez que ce sélecteur doit être précédé d'un dièse.** Cela dit, quand on précise le nom de l'id dans l'attribut **id**, on ne met pas de dièse.

**La différence avec une classe :** On ne peut l'appliquer qu'à **un seul élément** par page Web !

---

### Classes et IDs multiples

**Tous les éléments HTML peuvent avoir un id et / ou une classe.**

**Un élément HTML peut avoir plusieurs classes** et un seul id.

Séparez simplement vos classes par des espaces :

```html
<p class="classe1 classe2">Paragraphe en jaune.</p>
```

---

## ⚖️ Priorité des sélecteurs

### Question de priorité

**De quelle couleur sera chaque paragraphe ?**

```html
<style>
    .blue {color: blue;}
    #red {color: red;}
    p {color: goldenrod; font-weight:bold;}
</style>

<p class="blue">Paragraphe 1</p>
<p>Paragraphe 2</p>
<p class="blue" id="red">Paragraphe 3</p>
<p style="color:greenyellow;" id="red">Paragraphe 4</p>
```

<!-- ![Question priorité](../../static/img/1/question-priorite.png) -->

---

### Réponse : Priorité des sélecteurs

S'il y a un conflit de style, la priorité respectée sera la suivante :

**Style intraligne > ID > Classe > Élément**

```css
#un_id {color: red;}
.une_classe {color: blue;}
p {color: green;}
```

**Réponses :**

```html
<p class="blue">Paragraphe 1</p>              <!-- Bleu -->
<p>Paragraphe 2</p>                            <!-- Goldenrod (gras) -->
<p class="blue" id="red">Paragraphe 3</p>     <!-- Rouge -->
<p style="color:greenyellow;" id="red">Paragraphe 4</p>  <!-- Vert-jaune -->
```

<!-- ![Réponse priorité](../../static/img/1/reponse-priorite.png) -->

**Rendu :**
- Paragraphe 1 (bleu)
- Paragraphe 2 (goldenrod gras)
- Paragraphe 3 (rouge)
- Paragraphe 4 (vert-jaune)

---

## 📄 CSS externe

### Manière #3 : CSS externe

Fonctionne exactement comme le CSS interne... mais au lieu de glisser du CSS dans `<style>` dans le `<head>`... on va l'insérer dans **un autre fichier**.

C'est un fichier avec l'extension **.css**

On y glisse nos sélecteurs et nos règles CSS comme dans le `<head>`, mais on doit insérer une ligne supplémentaire au tout début :

```css
@charset "UTF-8";
```

**Cette ligne sert simplement à indiquer la famille de caractères du fichier CSS.**

<!-- ![CSS externe fichier](../../static/img/1/css-externe-fichier.png) -->

---

### Lier le fichier CSS à la page HTML

Par contre, ce fichier doit être « associé » à notre page Web pour fonctionner.

On utilise pour ça l'élément **link** dans le `<head>` :

```html
<head>
    <meta charset="UTF-8">
    <title>Page d'exemple</title>
    <link rel="stylesheet" href="styles.css">
</head>
```

**Ce lien relatif vers notre fichier CSS externe** fonctionne comme les éléments **img** et les éléments **a** !

<!-- ![Lien CSS externe](../../static/img/1/lien-css-externe.png) -->

Cet attribut permet de spécifier le type de relation avec le fichier associé. Dans ce cas-ci, c'est une feuille de styles.

---

## 🤔 Quelle manière faut-il privilégier ?

### Les 3 méthodes comparées

**CSS externe** (fichier séparé) : **À privilégier !** 
- Cela permet de réunir le CSS de plusieurs pages Web dans un seul fichier et cela encourage à uniformiser les styles d'un site Web avec plusieurs pages.

**CSS interne** (dans le `<head>`) : **À éviter**, mais parfois pratique
- Si une page Web se distingue fortement des autres en raison d'un événement particulier... Cela évite de mettre du CSS qui ne servira qu'à une seule page dans un fichier commun.

**CSS intraligne** (dans la balise concernée avec `style="..."`) : **À éviter !**
- Si un élément est très particulier et a besoin d'une règle unique, le CSS Intraligne dépanne... mais il faut tenter de trouver une solution plus globale si possible.

:::info Information
Dans le cadre du cours, nous utiliserons les trois manières à des fins pédagogiques.
:::

---

## 📦 Éléments de groupement

### Introduction

Disons qu'on souhaite appliquer un style à quelques paragraphes précis...

**Sans élément de groupement :**

```html
<head>
    <meta charset="UTF-8">
    <title>Page d'exemple</title>
    <style>
        .blue {
            color: blue;
        }
    </style>
</head>

<h1>Titre de la page</h1>

<p>Un premier paragraphe.</p>
<p>Un deuxième paragraphe.</p>
<p class="blue">Un troisième paragraphe.</p>
<p class="blue">Un quatrième paragraphe.</p>
<p class="blue">Un deuxième paragraphe.</p>
<p>Un sixième paragraphe.</p>
```

<!-- ![Sans groupement](../../static/img/1/sans-groupement.png) -->

**Rendu :**
- Titre de la page
- Un premier paragraphe.
- Un deuxième paragraphe.
- Un troisième paragraphe. (bleu)
- Un quatrième paragraphe. (bleu)
- Un cinquième paragraphe. (bleu)
- Un sixième paragraphe.

---

### Élément `<div>`

L'élément **div** permet (entre autre) d'appliquer un style à plusieurs balises simultanément.

**Exemple :**

```html
<h1>Titre de la page</h1>

<p>Un premier paragraphe.</p>
<p>Un deuxième paragraphe.</p>
<div class="blue">
    <p>Un troisième paragraphe.</p>
    <p>Un quatrième paragraphe.</p>
    <p>Un cinquième paragraphe.</p>
</div>
<p>Un sixième paragraphe.</p>
```

<!-- ![Avec div](../../static/img/1/avec-div.png) -->

**Rendu :**
- Titre de la page
- Un premier paragraphe.
- Un deuxième paragraphe.
- Un troisième paragraphe. (bleu)
- Un quatrième paragraphe. (bleu)
- Un cinquième paragraphe. (bleu)
- Un sixième paragraphe.

✅ **Pas besoin d'appliquer la classe à chaque élément p.**

---

### Élément `<span>`

L'élément **span** est similaire à div... mais pour une **portion de texte** !

**Exemple :**

```html
<p>J'aimerais que seul le mot <span class="rouge">span</span> soit coloré.</p>
```

```css
<head>
    <meta charset="UTF-8">
    <title>Page d'exemple</title>
    <style>
        .rouge {
            color: red;
        }
    </style>
</head>
```

<!-- ![Span exemple](../../static/img/1/span-exemple.png) -->

**Rendu :**
```
J'aimerais que seul le mot span soit coloré.
```
(le mot "span" est en rouge)

---

### Éléments sémantiques vs div/span

Il existe d'autres éléments de groupement, comme **div** et **span**... mais ils sont **sémantiques**.

Les éléments **div** et **span** ne sont pas sémantiques : Ils sont **utilitaires / pratiques**, ils nous permettent de grouper du texte ou des éléments.

Les éléments **header**, **nav**, **main** et **footer** sont sémantiques : Ils donnent une signification aux éléments qu'ils regroupent et ne devrait être utilisés qu'une fois par page Web chacun. (Sauf nav)

**En terme d'utilité, ils sont similaires à div :** Ils regroupent des éléments.

**Cependant, sémantique / signification qu'ils apportent à leur section de la page Web offre des avantages au niveau de l'accessibilité** (Accès au contenu pour les utilisateurs avec handicap).

:::warning Attention
En terme d'utilité, ils sont similaires à **div** : Ils regroupent des éléments.
:::

---

## 🏛️ Éléments sémantiques HTML5

### Élément `<header>`

**En-tête de la page**. Souvent commun à toutes les pages d'un site Web. Contient titres, bannières, logos, etc.

Encadré en rouge ici :

```html
<header>
    <!-- Contenu du header -->
</header>
```

<!-- ![Header exemple](../../static/img/1/header-exemple.png) -->

**Exemple visuel :**
Site w3schools.com avec le header encadré en rouge (logo HTML, bannière verte "Next")

---

### Élément `<nav>`

Contient le **menu de navigation** (généralement avec des boutons) vers les autres pages principales du site Web.

Parfois intégré à l'intérieur du **header**, parfois non.

Parfois horizontal, parfois vertical.

Encadré en rouge dans l'extrait ci-contre :

Il peut y en avoir plusieurs dans une page.

```html
<nav>
    <!-- Contenu du nav -->
</nav>
```

<!-- ![Nav exemple](../../static/img/1/nav-exemple.png) -->

**Exemple visuel :**
Menu de navigation horizontal (HTML, CSS, JAVASCRIPT, SQL, PYTHON, JAVA, PHP, etc.)

---

### Élément `<footer>`

**Pied de page**, souvent commun à toutes les pages d'un site Web. Contient logo, copyrights, « à propos », etc.

Encadré en rouge ici :

```html
<footer>
    <!-- Contenu du footer -->
</footer>
```

<!-- ![Footer exemple](../../static/img/1/footer-exemple.png) -->

**Exemple visuel :**
Footer avec plusieurs colonnes de liens, copyright, etc.

---

### Élément `<main>`

Contenu qui varie grandement d'une page à l'autre.

C'est toutes les informations propres à **une page** et non au site au complet.

Potentiellement très vaste.

Encadré en rouge ici :

```html
<main>
    <!-- Contenu du main -->
</main>
```

<!-- ![Main exemple](../../static/img/1/main-exemple.png) -->

**Exemple visuel :**
Section principale avec "HTML Tutorial", paragraphe, exemples de code

---

## 🎨 Styles de base - Couleurs

### Introduction

Pour conclure, abordons quelques styles CSS de base :

- **Styles colores**
- **Styles de texte**
- **Styles de police** 🤷‍♂️

Pour les curieux / étudiants qui ne dorment pas :

Liste de tous les styles CSS : **https://www.w3schools.com/cssref/**

---

### Règle `color`

Change la **couleur du texte**.

```html
<p style="color:mediumturquoise;">Ce texte est coloré. C'est excitant !</p>
```

<!-- ![Color exemple](../../static/img/1/color-exemple.png) -->

**Rendu :**
```
Ce texte est coloré. C'est excitant !
```
(en turquoise moyen)

---

### Règle `background-color`

Change la **couleur de fond** d'un élément.

```html
<h2>Le CSS c'est trépidant.</h2>

<div style="background-color:mistyrose;">
    <p>La couleur de fond sous ce texte a été modifiée.</p>
    <p>C'est incroyable !</p>
</div>
```

<!-- ![Background-color exemple](../../static/img/1/background-color-exemple.png) -->

**Rendu :**
```
Le CSS c'est trépidant.

[Fond rose pâle]
La couleur de fond sous ce texte a été modifiée.
C'est incroyable !
```

---

### Règle `border`

Encadre un élément / du texte avec une bordure.

**Syntaxe :**

```css
border: [style] [couleur] [largeur];
```

**Types de bordure :** Elle est **continue** ou elle **n'est pas continue** (dashed, dotted, double...)

**Couleur de la bordure**

**Largeur de la bordure** (ici, mesurée en pixels)

```css
<style>
    .special {
        border: orchid solid 2px;
    }
</style>

<p>Certains mots sont si <span class="special">spéciaux</span> qu'on peut les encadrer.</p>
```

<!-- ![Border exemple](../../static/img/1/border-exemple.png) -->

**Rendu :**
```
Certains mots sont si [spéciaux] qu'on peut les encadrer.
```
(avec bordure orchidée)

---

### Comment choisir une couleur PRÉCISE ?

On peut utiliser un des **145 noms de couleurs** que CSS connaît... (blue, red, yellow, green, rebeccapurple, saddlebrown, peru, etc.)

Ou utiliser le **code hexadécimal** d'une couleur précise :

```css
.special {
    color: #e05eb3;
}
```

<!-- ![Color picker](../../static/img/1/color-picker.png) -->

**Pipette à couleurs en ligne :**
https://htmlcolorcodes.com/color-picker/

---

## ✍️ Styles de texte

### Règle `text-align`

Change **l'alignement horizontal** d'un texte. (Options : left, center, right, justify)

```html
<p style="text-align:left;">Ce texte est aligné par défaut.</p>
<p style="text-align:right;">Ce texte est aligné à droite.</p>
<p style="text-align:center;">Ce texte est aligné au centre.</p>
```

<!-- ![Text-align exemple](../../static/img/1/text-align-exemple.png) -->

**Rendu :**

```
Vive le vent !

Ce texte est aligné par défaut.
                        Ce texte est aligné à droite.
            Ce texte est aligné au centre.
```

---

### Règle `text-decoration`

Permet de mettre un trait sur / à travers / sous le texte. (Options : underline, overline, line-through, none)

```html
<p>Ce texte n'a pas de trait.</p>
<p style="text-decoration:underline;">Ce texte est souligné.</p>
<p style="text-decoration:line-through;">Ce texte est rayé.</p>
```

<!-- ![Text-decoration exemple](../../static/img/1/text-decoration-exemple.png) -->

**Rendu :**
```
Ce texte n'a pas de trait.
Ce texte est souligné. (souligné)
Ce texte est rayé. (barré)
```

---

### Règle `text-transform`

Détermine si le texte est en majuscules / minuscules. (Options : lowercase, uppercase, capitalize)

```html
<p style="text-transform:uppercase;">Ce texte est en majuscules.</p>
<p style="text-transform:lowercase;">Ce TEXTE SERA EN MINUSCULES.</p>
<p style="text-transform:capitalize;">Ce Texte Sera Similaire À Un Titre En Anglais.</p>
```

<!-- ![Text-transform exemple](../../static/img/1/text-transform-exemple.png) -->

**Rendu :**
```
CE TEXTE EST EN MAJUSCULES.

ce texte sera en minuscules.

Ce Texte Sera Similaire À Un Titre En Anglais.
```

---

## 🔤 Styles de police

### Règle `font-family`

Détermine la **famille de police** du texte (Les options sont TRÈS nombreuses : Times New Roman, Verdana, Calibri, Courrier New, etc.)

```html
<p style="font-family:Verdana;">"Times New Roman";</p>

<p>Ce texte est en majuscules.</p>
```

<!-- ![Font-family exemple](../../static/img/1/font-family-exemple.png) -->

**On peut ordonner plusieurs polices en les séparant par des virgules.** Si jamais la première police n'est pas disponible dans le navigateur, la suivante sera utilisée.

**Une police qui doit être écrite en plusieurs mots doit être encadrée avec des apostrophes.**

Cela ne se voit peut-être pas, mais ce texte est en Verdana.

:::warning Attention
Une police qui doit être écrite en plusieurs mots doit **être encadrée avec des apostrophes**.
:::

---

### Règle `font-style`

Règle qui détermine « **à quel point une police est penchée / italique** ».

(Options : normal, italic, oblique)

```html
<p style="font-style:normal;">Les lettres sont stables.</p>
<p style="font-style:italic;">Les lettres font comme Michael Jackson.</p>
<p style="font-style:oblique;">Les lettres ont peur de tomber.</p>
```

<!-- ![Font-style exemple](../../static/img/1/font-style-exemple.png) -->

**Rendu :**
```
Les lettres sont stables.
Les lettres font comme Michael Jackson. (italique)
Les lettres ont peur de tomber. (oblique)
```

---

### Règle `font-size`

Détermine la **taille du texte**. Calculé en **pixels** ou en **em**. 1 em = taille ordinaire, 2 em = double de la taille ordinaire.

```html
<p style="font-size:1em;">Texte de taille ordinaire.</p>
<p style="font-size:2em;">Texte deux fois plus grand.</p>
<p style="font-size:200px;">Texte un peu grand.</p>
```

<!-- ![Font-size exemple](../../static/img/1/font-size-exemple.png) -->

**Rendu :**
```
Vive le vent !

Texte de taille ordinaire.

Texte deux fois plus grand.

Texte un peu grand.
```

---

## 📝 Résumé de la partie CSS

### Concepts clés

1. **CSS** = Cascading Style Sheet (Feuille de style en cascade)
2. CSS décrit **comment afficher les éléments HTML**
3. Une règle CSS = **attribut: valeur;**
4. **3 méthodes** d'application : Intraligne, Interne, Externe
5. **3 types de sélecteurs** principaux : Élément, Classe, ID
6. **Priorité** : Style intraligne > ID > Classe > Élément

---

### Les 3 méthodes d'application CSS

| Méthode | Syntaxe | Recommandation |
|---------|---------|----------------|
| **CSS Intraligne** | `<p style="color:red;">` | ⚠️ À éviter (sauf cas particulier) |
| **CSS Interne** | `<style>` dans `<head>` | ⚠️ À éviter (sauf page unique) |
| **CSS Externe** | Fichier `.css` + `<link>` | ✅ **À privilégier !** |

---

### Les sélecteurs CSS

| Type | Syntaxe | Utilisation | Exemple |
|------|---------|-------------|---------|
| **Élément** | `p { }` | Tous les éléments du type | `p { color: blue; }` |
| **Classe** | `.nom { }` | Plusieurs éléments | `<p class="nom">` |
| **ID** | `#nom { }` | Un seul élément par page | `<p id="nom">` |

**Priorité :** Style intraligne > ID > Classe > Élément

---

### Éléments de groupement

| Élément | Type | Description |
|---------|------|-------------|
| `<div>` | Générique (bloc) | Conteneur pour grouper plusieurs éléments |
| `<span>` | Générique (inline) | Conteneur pour une portion de texte |
| `<header>` | Sémantique | En-tête de la page |
| `<nav>` | Sémantique | Menu de navigation |
| `<main>` | Sémantique | Contenu principal |
| `<footer>` | Sémantique | Pied de page |

:::info Information
Les éléments **sémantiques** (header, nav, main, footer) offrent des avantages pour l'**accessibilité**.
:::

---

### Styles de base - Couleurs

| Propriété | Description | Exemple |
|-----------|-------------|---------|
| `color` | Couleur du texte | `color: blue;` |
| `background-color` | Couleur de fond | `background-color: lightblue;` |
| `border` | Bordure | `border: solid black 2px;` |

**Formats de couleurs :**
- **Noms** : `red`, `blue`, `rebeccapurple` (145 noms)
- **Hexadécimal** : `#FF5733`, `#e05eb3`
- **RGB** : `rgb(255, 87, 51)`

**Outil recommandé :** https://htmlcolorcodes.com/color-picker/

---

### Styles de texte

| Propriété | Description | Valeurs possibles |
|-----------|-------------|-------------------|
| `text-align` | Alignement horizontal | `left`, `center`, `right`, `justify` |
| `text-decoration` | Décoration du texte | `none`, `underline`, `overline`, `line-through` |
| `text-transform` | Transformation du texte | `none`, `uppercase`, `lowercase`, `capitalize` |

**Exemples :**

```css
text-align: center;          /* Centre le texte */
text-decoration: underline;  /* Souligne le texte */
text-transform: uppercase;   /* MAJUSCULES */
```

---

### Styles de police

| Propriété | Description | Exemple |
|-----------|-------------|---------|
| `font-family` | Famille de police | `font-family: Arial, sans-serif;` |
| `font-size` | Taille du texte | `font-size: 16px;` ou `font-size: 1em;` |
| `font-style` | Style du texte | `font-style: italic;` |
| `font-weight` | Épaisseur du texte | `font-weight: bold;` |

**Notes importantes :**

✅ Pour `font-family`, on peut lister plusieurs polices séparées par des virgules

✅ Les polices avec espaces doivent être entre apostrophes : `'Times New Roman'`

✅ `font-size` : 1em = taille normale, 2em = double

---

### Bonnes pratiques CSS

✅ **Privilégier le CSS externe** pour faciliter la maintenance

✅ **Utiliser des noms de classes descriptifs** (.titre-principal, .bouton-rouge)

✅ **Éviter les IDs pour le style**, préférer les classes

✅ **Utiliser les éléments sémantiques** (header, nav, main, footer) quand approprié

✅ **Grouper les styles similaires** pour éviter la répétition

✅ **Commenter votre CSS** pour expliquer les sections complexes

---

## 🎯 Fin de la partie CSS

**Félicitations !** Vous maîtrisez maintenant les bases de CSS ! 🎉

Vous savez :
- ✅ Appliquer du CSS de 3 façons différentes
- ✅ Utiliser les sélecteurs (élément, classe, id)
- ✅ Comprendre la priorité des styles
- ✅ Organiser votre code avec div, span et éléments sémantiques
- ✅ Styliser les couleurs, textes et polices

---

**Ressources utiles :**

📚 **Liste complète des propriétés CSS :** https://www.w3schools.com/cssref/

🎨 **Sélecteur de couleurs :** https://htmlcolorcodes.com/color-picker/

📖 **Documentation CSS :** https://developer.mozilla.org/fr/docs/Web/CSS

---

**Prochaines étapes :**

Avec HTML et CSS maîtrisés, vous pouvez maintenant :
- 🎨 Créer des pages Web attractives et bien structurées
- 📱 Apprendre le responsive design (adaptation mobile)
- 🎭 Découvrir les animations CSS
- 📦 Explorer les layouts avancés (Flexbox, Grid)
- ✨ Ajouter de l'interactivité avec JavaScript

---