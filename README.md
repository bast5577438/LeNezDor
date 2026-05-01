# 🥇 Nez d'Or — Cérémonie de Remise de Prix

Page web événementielle créée pour la **Biscuiterie Louvat**, à destination des employés chargés d'animer la soirée de remise des « Lunettes Géantes ».

---

## 🎯 Contexte du projet

La Biscuiterie Louvat organise un jeu original : dans 10 paquets de biscuits « lunettes », une lunette avec un **nez d'or** est glissée au hasard. Les 10 clients qui la trouvent sont invités à une **soirée de remise de prix** où ils repartent avec une **lunette géante en biscuit**.

Ce site sert de **feuille de route digitale** pour les employés qui orchestrent la soirée : ils peuvent suivre le déroulé étape par étape et cocher chaque action au fil du temps.

---

## ✨ Fonctionnalités

- **Page d'accueil (Hero)** — Titre animé, emblème SVG dessiné à la main, informations clés de la soirée
- **Palmarès des lauréats** — Grille de 10 cartes avec classement, prénom, nom et accompagnant(s)
- **Timeline interactive** — 10 étapes de 17h à 21h15, cochables en temps réel
- **Barre de progression** — Affiche le nombre d'étapes validées sur 10
- **Persistance locale** — L'état des cases cochées est sauvegardé dans le `localStorage` du navigateur
- **Animations au scroll** — Les sections apparaissent progressivement à l'aide d'un `IntersectionObserver`
- **Design responsive** — Adapté mobile et desktop

---

## 🗂️ Structure du projet

```
nez-dor/
└── index.html   # Fichier unique — HTML, CSS et JS intégrés
```

Le projet est intentionnellement **mono-fichier** pour faciliter le déploiement et la distribution aux équipes (aucune dépendance à installer, aucun serveur nécessaire).

---

## 🚀 Utilisation

### Ouvrir localement
Aucune installation requise. Il suffit d'ouvrir `index.html` dans un navigateur.

```bash
# Cloner le dépôt
git clone https://github.com/votre-utilisateur/nez-dor.git

# Ouvrir le fichier
open nez-dor/index.html
```

### Déployer en ligne
Le fichier peut être hébergé sur n'importe quelle plateforme statique :
- **GitHub Pages** — Activer dans les paramètres du dépôt (Settings → Pages)
- **Netlify / Vercel** — Glisser-déposer le fichier dans l'interface

---

## 🛠️ Personnalisation

Toutes les modifications se font directement dans `index.html`.

### Changer les lauréats
Repérer la section `<!-- WINNERS -->` et modifier les blocs `.winner-card` :

```html
<div class="winner-card">
  <div class="rank">1</div>
  <div class="laurel">❦ ❦ ❦</div>
  <h3>Prénom</h3>
  <div class="surname">NOM</div>
  <!-- Optionnel : supprimer la ligne suivante si le lauréat vient seul -->
  <div class="accompagnant">Accompagné(e) de ...</div>
</div>
```

### Modifier le programme
Repérer la section `<!-- PROGRAM -->` et ajuster les étapes dans `.timeline-item`. Ajouter la classe `highlight` pour mettre une étape en valeur :

```html
<div class="timeline-item highlight" data-id="X">
  <div class="timeline-time">19h30</div>
  ...
</div>
```

> ⚠️ Si le nombre total d'étapes change, mettre à jour le compteur `/ 10 étapes` dans le HTML et la logique JS si nécessaire.

### Changer les couleurs
Les couleurs sont centralisées dans les variables CSS en haut du `<style>` :

```css
:root {
  --gold: #c9a961;
  --gold-dark: #a88841;
  --gold-light: #e8d5a0;
  --cream: #faf6ee;
  --ink: #1a1410;
  --ink-soft: #3d342a;
  --paper: #fffdf7;
}
```

---

## 🧰 Technologies

| Technologie | Usage |
|-------------|-------|
| HTML5 sémantique | Structure de la page |
| CSS3 (variables, grid, flexbox, animations) | Mise en page et design |
| JavaScript vanilla | Checklist interactive, localStorage, IntersectionObserver |
| SVG inline | Emblème et icônes dessinés à la main |
| Google Fonts | Cormorant Garamond + Inter |

Aucun framework, aucune bibliothèque externe — **zéro dépendance**.

---

## 📄 Licence

Projet réalisé pour usage interne — **Biscuiterie Louvat**, 2026.
