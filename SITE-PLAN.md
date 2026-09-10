# Plan du site — L'Écrin Céline (boutique de goodies hommage à Céline Dion)

> ⚠️ **Point d'attention légal** : ce site vend des produits dérivés au nom et à l'image d'une célébrité vivante sans licence officielle. Le nom de marque ("L'Écrin Céline" plutôt que "Boutique Céline Dion"), le mot "hommage", et le disclaimer de non-affiliation (présent dans chaque footer et en FAQ) sont des protections minimales, pas une garantie légale. Avant de vendre réellement, faites valider l'usage du nom/image par un avocat spécialisé en propriété intellectuelle — le droit à l'image et le droit des marques s'appliquent même à des produits "hommage".

**Audience cible :** fans de Céline Dion
**Objectif principal :** générer des ventes de goodies (conversion e-commerce)

---

## 1. Architecture du site

| Page | Rôle | Objectif de conversion |
|---|---|---|
| **Accueil** (`index.html`) | Vitrine, accroche, réassurance | Clic vers la boutique / ajout au panier |
| **Boutique / Nos goodies** (`services.html`) | Présente les 3 catégories de produits | Ajout au panier |
| **Fiche produit** *(à construire par catégorie)* | Détail, photos, avis, variantes | Achat |
| **À propos** (`about.html`) | Histoire, mission, valeurs, confiance | Clic vers la boutique |
| **FAQ** (intégrée à l'accueil, ancre `#faq`) | Lève les objections avant achat | Réduction de l'abandon de panier |
| **Panier / Commande** *(à brancher sur une solution e-commerce : Shopify, Snipcart, etc.)* | Tunnel d'achat | Achat finalisé |
| **Mentions légales / CGV** *(à créer)* | Conformité, confiance, obligation légale | Confiance / conformité |
| **Contact** *(à créer)* | SAV, questions pré-achat | Réponse aux objections restantes |
| **Blog / Actu Céline Dion** *(optionnel, SEO)* | Contenu éditorial autour du mot-clé "Céline Dion" | Trafic organique → boutique |

**Structure de navigation idéale :** Accueil → Boutique → À propos → FAQ, avec le panier toujours visible dans le header. Le blog, s'il est créé, alimente la boutique via des liens internes plutôt que d'être une destination finale.

---

## 2. Pourquoi cet ordre sur la page d'accueil

1. **Hero** — capter l'attention en moins de 8 secondes et répondre tout de suite à l'objection n°1 (authenticité/qualité), avant que le visiteur ne descende ou reparte.
2. **Bandeau confiance** — juste après le hero, pour rassurer un visiteur encore méfiant *avant* de lui présenter l'offre commerciale (sinon il la lit avec suspicion).
3. **Services / catégories de produits** — une fois la confiance posée, on peut enfin montrer concrètement ce qu'on vend.
4. **Preuve sociale (témoignages)** — juste avant que le visiteur envisage sérieusement d'acheter : on fait dire par d'autres fans ce que la marque ne peut pas dire elle-même de façon crédible.
5. **FAQ** — désamorce les toutes dernières objections (délais, retours, "est-ce officiel ?") juste avant l'appel à l'action final.
6. **CTA final** — la dernière chose vue par un visiteur qui n'a pas encore cliqué : un message simple, sans ambiguïté sur l'étape suivante.

Cet ordre suit la logique **attention → confiance → offre → preuve → objections → action**, qui est la séquence de conversion la plus stable pour un site e-commerce grand public.

---

## 3. Système visuel (résumé — détail complet dans `styles.css`)

- **Couleur primaire :** Bordeaux `#7A1F3D` (élégance, glamour scène) + Doré `#C9A24B` (luxe, CTA)
- **Couleur secondaire :** Noir `#1A1A1A` (texte), Blanc cassé `#FAF7F2` (fond), Taupe `#8C8577` (texte secondaire)
- **Polices :** Titres en *Playfair Display* (serif élégant, effet "diva"), corps en *Inter* (sans-serif moderne, très lisible)
- **Boutons :** coins arrondis (10px), fond doré pour l'action principale, contour bordeaux pour l'action secondaire, léger effet de soulèvement au survol
- **Espacement :** grille de base 8px (8/16/24/32/48/64/96)
- **Direction image :** photos lifestyle chaleureuses + packshots produits sur fond neutre, touches dorées en accent
- **Ambiance générale :** élégant, chaleureux, digne d'une diva mais accessible — jamais froid ni générique

Ce système est appliqué dans `styles.css` et repris sur les 3 pages (`index.html`, `services.html`, `about.html`), donc modifiable en un seul endroit.

---

## 4. Fichiers du projet

- `index.html` — page d'accueil (hero, confiance, services, preuve sociale, FAQ, CTA final)
- `services.html` — page boutique avec les 3 catégories de goodies (porte-clés, mugs, t-shirts)
- `about.html` — page À propos (histoire, mission, valeurs, différenciation)
- `styles.css` — système de style complet (couleurs, typographie, composants), commenté et modifiable sans développeur

## 5. Prochaines étapes suggérées

1. Remplacer les blocs "Photo produit" par de vraies photos.
2. Brancher un vrai panier/paiement (Shopify, Snipcart, Stripe Checkout…).
3. Créer les pages Mentions légales / CGV / Contact.
4. Faire valider les visuels et le nom de marque par un avocat avant mise en ligne commerciale réelle.
