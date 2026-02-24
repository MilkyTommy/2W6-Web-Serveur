---
title: Positionnement, pseudo-classes, sélecteurs complexes & priorité CSS
description: Cours 2.2 - Positionnement, sélecteurs complexes & priorité CSS
---

# Positionnement, pseudo-classes, sélecteurs complexes & priorité CSS

## 📋 Table des matières

1. [Le flux normal (avant de positionner)](#-le-flux-normal-avant-de-positionner)
2. [La propriété position](#-la-propriété-position)
   1. [static](#static)
   2. [relative](#relative)
   3. [fixed](#fixed)
   4. [sticky](#sticky)
   5. [absolute](#absolute)
3. [La propriété z-index](#-la-propriété-z-index)
4. [Pseudo-classes : hover et active](#-pseudo-classes--hover-et-active)
5. [Sélecteurs complexes](#-sélecteurs-complexes)
   1. [Sélecteur enfant (>) ](#-sélecteur-enfant-)
   2. [Sélecteur combiné (,)](#-sélecteur-combiné-)
6. [Quelques règles CSS utiles](#-quelques-règles-css-utiles)
7. [Priorité en CSS (spécificité) + ordre des règles](#-priorité-en-css-spécificité--ordre-des-règles)

---

## 🌊 Le flux normal (avant de positionner)

Par défaut, les éléments se placent selon le **flux normal** du document :

- Les éléments **block** s’empilent verticalement
- Les éléments **inline** s’insèrent sur une ligne tant qu’il y a de l’espace

<!-- Image(s) : slide "Pour le moment... les éléments se positionnent en suivant le flot du code HTML"
- ../../static/img/4/flot-normal.png
-->

---

## 📌 La propriété position

La propriété `position` contrôle comment un élément est positionné.

Valeurs vues dans les diapositives :

1. [static](#static) (**par défaut**)
2. [relative](#relative)
3. [fixed](#fixed)
4. [sticky](#sticky)
5. [absolute](#absolute)

On utilise ensuite souvent : `top`, `right`, `bottom`, `left`.

---

### static

- Valeur **par défaut**
- L’élément reste dans le **flux normal**
- `top/right/bottom/left` n’ont pas d’effet (en général)

```css
.boite {
  position: static;
}
```

<!-- Image(s) : exemple position static (boîtes colorées)
- ../../static/img/4/position-static.png
-->

---

### relative

- L’élément **garde sa place** dans le flux normal
- MAIS on peut le **décaler** avec `top/right/bottom/left`
- Son espace initial est toujours réservé

```css
.boite {
  position: relative;
  top: 20px;
  left: 30px;
}
```

<!-- Image(s) : exemple position relative (décalage)
- ../../static/img/4/position-relative.png
-->

---

### fixed

- L’élément est positionné **par rapport au viewport**
- Il reste en place même quand on scrolle
- Exemple typique : bouton “retour en haut”, menu fixe, badge, etc.

```css
.bouton {
  position: fixed;
  bottom: 20px;
  right: 20px;
}
```

<!-- Image(s) : exemple position fixed
- ../../static/img/4/position-fixed.png
-->

---

### sticky

- Entre `relative` et `fixed`
- L’élément se comporte normalement puis devient “collant” lors du scroll (selon un seuil `top: ...`)

```css
.menu {
  position: sticky;
  top: 0;
}
```

<!-- Image(s) : exemple position sticky
- ../../static/img/4/position-sticky.png
-->

---

### absolute

- L’élément sort du flux normal
- Il se positionne par rapport :
  - au **premier ancêtre positionné** (non-static), sinon
  - au viewport / document (selon les cas)
- Utile pour placer précisément un élément dans un conteneur

```css
.badge {
  position: absolute;
  top: 10px;
  right: 10px;
}
```

:::warning Attention
Si tu veux qu’un `absolute` se positionne *dans* un parent, mets souvent le parent en `position: relative;`.
:::

<!-- Image(s) : exemples position absolute + parent
- ../../static/img/4/position-absolute-1.png
- ../../static/img/4/position-absolute-2.png
-->

---

## 🥞 La propriété z-index

`z-index` gère la “profondeur” : qui passe par-dessus qui.

- Fonctionne seulement sur des éléments positionnés (`relative`, `absolute`, `fixed`, `sticky`).
- Plus le `z-index` est grand, plus l’élément est “devant”.

```css
.devant {
  position: relative;
  z-index: 10;
}

.derriere {
  position: relative;
  z-index: 1;
}
```

<!-- Image(s) : exemple z-index + superposition
- ../../static/img/4/z-index.png
-->

---

## 🧪 Pseudo-classes : hover et active

Les pseudo-classes décrivent l’**état** d’un élément.

### `:hover`

Quand la souris passe au-dessus.

```css
a:hover {
  color: white;
  background-color: black;
}
```

<!-- Image(s) : exemple hover
- ../../static/img/4/pseudo-hover.png
-->

### `:active`

Pendant le clic (l’instant où l’élément est activé).

```css
a:active {
  transform: scale(0.98);
}
```

<!-- Image(s) : exemple active
- ../../static/img/4/pseudo-active.png
-->

---

## 🧠 Sélecteurs complexes

Avant, on a vu :
- élément : `p`
- classe : `.maClasse`
- id : `#monId`

Maintenant, on ajoute des sélecteurs plus “intelligents”.

### 👶 Sélecteur enfant (>)

Sélectionne les **enfants directs**.

```css
div > p {
  border: 2px solid black;
}
```

<!-- Image(s) : exemple div > p
- ../../static/img/4/selecteur-enfant.png
-->

### 🧷 Sélecteur combiné (,)

Permet de grouper plusieurs sélecteurs qui partagent des règles.

```css
h1, h2, p {
  background-color: burlywood;
}
```

<!-- Image(s) : exemple h1, h2, p
- ../../static/img/4/selecteur-combinaison.png
-->

---

## 🧰 Quelques règles CSS utiles

Ces règles apparaissent comme “nouveaux outils” :

### min/max width/height

- `max-width` / `max-height` : limite la taille maximale
- `min-width` / `min-height` : impose une taille minimale

### cursor

Change le curseur :

```css
button {
  cursor: pointer;
}
```

### opacity

```css
img {
  opacity: 0.5;
}
```

### box-shadow

```css
.card {
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
}
```

### transition

Anime une transition entre deux états (souvent `:hover`).

```css
.boite {
  transition: background-color 0.5s, color 0.5s;
}

.boite:hover {
  background-color: dimgray;
  color: white;
}
```

<!-- Image(s) : slides "Quelques règles CSS" + démonstrations
- ../../static/img/4/regles-max-min.png
- ../../static/img/4/regle-cursor.png
- ../../static/img/4/regle-opacity.png
- ../../static/img/4/regle-box-shadow.png
- ../../static/img/4/regle-transition.png
-->

---

## 🏆 Priorité en CSS (spécificité) + ordre des règles

Quand plusieurs règles s’appliquent au même élément, CSS doit choisir laquelle “gagne”.

### Rappel simplifié (déjà vu)

- CSS intraligne (`style="..."`)
- ID (`#...`)
- Classe (`.`)

### Version plus réaliste (vue dans les slides)

De manière générale, on peut retenir :

- **CSS intraligne** a une priorité très forte
- Puis viennent des sélecteurs plus précis (ID, classes, attributs, pseudo-classes...)
- Puis les sélecteurs d’éléments (`p`, `div`, etc.)

:::info information
À spécificité égale, **la dernière règle écrite gagne**.
:::

---

### Sélecteurs d’attribut

Cibler selon un attribut :

```css
a[target="_blank"] {
  background-color: black;
  color: white;
}
```

Ou cibler les éléments qui possèdent simplement un attribut :

```css
a[class] {
  background-color: black;
  color: white;
}
```

<!-- Image(s) : exemples attributs target/class
- ../../static/img/4/selecteur-attribut-target.png
- ../../static/img/4/selecteur-attribut-class.png
-->

---

### Pseudo-éléments

Un pseudo-élément cible une **partie** d’un élément.

Exemple :

```css
p::first-letter {
  color: red;
  font-weight: bold;
}
```

<!-- Image(s) : pseudo-élément first-letter
- ../../static/img/4/pseudo-element-first-letter.png
-->

---

### En cas d’égalité : la dernière règle gagne

Si deux règles ont la même spécificité, la dernière l’emporte.

Exemple (conceptuel) :

```css
p {
  color: red;
}

p {
  color: blue; /* gagne */
}
```

---

### CSS interne vs CSS externe

Si les sélecteurs ont la même spécificité, l’ordre (dans le HTML) peut faire la différence.

- si `<link rel="stylesheet" ...>` est après `<style>...</style>`, le CSS externe peut gagner
- si `<style>...</style>` est après `<link>`, le CSS interne peut gagner

<!-- Image(s) : slides “CSS interne VS CSS externe : CSS dernier gagne”
- ../../static/img/4/interne-vs-externe.png
-->

---