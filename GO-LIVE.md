# Checklist de mise en ligne — L'Écrin Céline

Le site est fonctionnellement prêt : panier, paiement et formulaire de contact
sont déjà branchés dans le code. Il reste des étapes de **configuration**
(comptes à créer, informations réelles à saisir) avant d'encaisser de vrais
paiements. Compte environ 30-45 minutes pour tout faire.

---

## 1. Héberger le site (5 min)

Le site est 100% statique (HTML/CSS), déployable tel quel sur :
- **Netlify** — glisser-déposer le dossier du projet sur app.netlify.com/drop
- **Vercel** — `vercel deploy` ou import du repo GitHub
- **GitHub Pages** — activer Pages sur ce repo, branche `claude/celine-dion-goodies-site-e160hz` (ou la merger sur `main`)

Une fois en ligne, tu obtiens une URL (ex. `ecrin-celine.netlify.app`), à
remplacer plus tard par un nom de domaine si tu en achètes un.

## 2. Activer le paiement réel — Snipcart (10-15 min)

Le panier est déjà intégré sur toutes les pages (`<div id="snipcart">` en bas
de chaque fichier HTML), il ne manque que la connexion à un vrai compte.

1. Crée un compte gratuit sur **snipcart.com**.
2. Dans son tableau de bord, va dans **Store Configuration → Payments** et
   active **Stripe** et/ou **PayPal** (Snipcart te guide pour lier ton propre
   compte Stripe/PayPal — c'est là que l'argent atterrit, pas chez Snipcart).
3. Récupère ta **clé API publique** (Account → API Keys → Public API key).
4. Dans les 6 fichiers HTML, remplace `VOTRE_CLE_API_PUBLIQUE_SNIPCART` par
   cette clé (recherche-remplace global, elle est identique partout).
5. Par défaut la clé est en mode **Test** : les paiements ne débitent
   personne. Dans le dashboard Snipcart, bascule sur la clé **Live** une fois
   que tu as vérifié qu'une commande test fonctionne de bout en bout.
6. Configure les **frais de livraison** dans Snipcart (Shipping methods) —
   sinon le panier bloque au moment de calculer la livraison.

Snipcart prélève une petite commission par vente (vérifie leur tarif actuel
sur snipcart.com/pricing) en plus des frais Stripe/PayPal habituels.

## 3. Formulaire de contact (2 min)

Le formulaire de `contact.html` est branché sur **FormSubmit.co** (gratuit,
sans compte).

1. Remplace `contact@ecrin-celine.fr` dans l'attribut `action` du formulaire
   (et dans le lien mailto juste à côté) par ta vraie adresse e-mail.
2. Envoie-toi un premier message de test depuis le formulaire en ligne : tu
   recevras un e-mail de confirmation FormSubmit à ouvrir une seule fois pour
   activer la réception. Sans ce clic, les messages suivants n'arrivent pas.

## 4. Informations légales réelles (10 min — important)

Deux pages contiennent des placeholders entre crochets à remplacer avant de
vendre pour de vrai — la vente en ligne en France impose des mentions
légales et des CGV exactes :

- `mentions-legales.html` : identité (nom, statut juridique, SIRET, adresse),
  hébergeur.
- `cgv.html` : nom de l'entreprise dans l'Article 1.

Si tu vends sans structure déclarée (pas d'auto-entreprise, pas de SIRET),
**ne mets pas le site en mode paiement réel** : en France, la vente
habituelle de biens contre rémunération nécessite un statut (auto-entreprise
au minimum). C'est rapide à créer (autoentrepreneur.urssaf.fr) mais c'est une
étape légale, pas juste un détail du site.

## 5. Photos produits (variable)

Dépose tes vraies photos dans le dossier `images/` avec les noms exacts
listés dans `images/README.md` (`porte-cles.jpg`, `mug.jpg`, `tshirt.jpg`).
Les blocs "Photo : ..." colorés sur les pages sont des placeholders CSS à
remplacer par de vraies balises `<img>` dans le HTML une fois les photos
prêtes (dis-le-moi et je le fais).

## 6. Prix et stock à ajuster si besoin

Les prix actuels (à changer directement dans `services.html` si besoin) :
- Porte-clés collector : 12,90 €
- Mug édition fan : 16,90 €
- T-shirt hommage : 24,90 € (avec sélecteur de taille XS→XXL)

Snipcart ne gère pas le stock par défaut : si un produit est en rupture,
retire temporairement son bouton "Ajouter au panier" ou ajoute
`data-item-max-quantity="0"` pour le désactiver.

## 7. Rappel — risque marque/droit à l'image (déjà signalé)

Vendre des produits au nom et à l'image de Céline Dion sans licence reste un
risque juridique réel, même avec la mention "non affilié" en footer. Cette
mention réduit le risque de confusion mais ne t'autorise pas légalement à
exploiter commercialement son nom/image. Avant d'ouvrir vraiment les ventes,
fais valider ça par un avocat en propriété intellectuelle — surtout si le
volume de ventes devient significatif.

---

**Une fois les étapes 1 à 4 faites, le site encaisse de vrais paiements.**
Les étapes 5 et 6 sont de la finition, pas des bloquants techniques.
