# Site « Le Petit Libraire » : mode d'emploi

Landing page qui réunit les livres d'Adèle Mercier sous l'identité « Le Petit Libraire ».
- **Fichiers à héberger** : `index.html` (un seul fichier, polices intégrées, aucun appel à Google Fonts) + `papa-couverture.jpg` + `frere-couverture.jpg` + `soeur-couverture.jpg` + `bellemere-couverture.jpg` dans le même dossier.
- **Aperçu privé sur claude.ai** : https://claude.ai/artifact/1PycAzFy7CSJpkT1AY1E1y (version 6 du 3 octobre 2026 : ajout de « Destination Belle-Maman »).

## 0. Livres présents (ordre d'affichage)
| Livre | Statut des contenus | Couverture affichée |
|---|---|---|
| Papi, à toi la parole ! | complet (sommaire, 26 extraits, 4 pages exemple) | dessinée (vert sapin) tant que `couverture` est vide |
| Avant d'être Mamie | complet (22 extraits, 3 pages exemple) | dessinée : renseigner `couverture: "mamie-couverture.png"` avec le PNG 1800 × 2700 déjà fourni |
| Papa, face B | complet (sommaire en 12 « pistes », 24 extraits, 3 pages exemple) | vraie couverture : `papa-couverture.jpg` |
| Frérot, mode coop | complet (sommaire en 12 « niveaux », 24 extraits, 3 pages exemple) | vraie couverture : `frere-couverture.jpg` |
| Sœurette, le numéro spécial | complet (sommaire en 12 « rubriques », 24 extraits, 3 pages exemple) | vraie couverture : `soeur-couverture.jpg` |
| **Destination Belle-Maman** *(ajouté, pastille « Nouveauté »)* | complet : sous-titre, points forts, sommaire en 12 « étapes », 24 extraits, 3 pages exemple ; fête des mères, Noël | **vraie couverture** : `bellemere-couverture.jpg` (640 × 960) |
| Maman, raconte-moi ton histoire | à compléter (voir § 3) | dessinée |

Ce qui change avec Destination Belle-Maman (version 6) :
- **Vitrine 3D** : Belle-Maman au premier plan (`vitrine: 1`), puis Sœurette (2) et Frérot (3). Papa sort de la vitrine (`vitrine: 0`) ; remets 1, 2 ou 3 pour l'y replacer.
- **Calendrier** : la fête des mères (dimanche 30 mai 2027) affiche « Pour Mamie, ta belle-mère, Maman » ; Noël liste les sept destinataires.
- **Extraits** : nouvel onglet « Pour ta belle-mère ». Le mot « Chapitre » devient « Étape » (`motChapitre: "Étape"`).
- **Questions au libraire** : Belle-Maman ajoutée dans « Faut-il aimer écrire ? », « Quel livre choisir ? » et « Quel est le format ? ».
- **Ruban des occasions** : ajout de « Un dimanche chez Belle-Maman ».
- La phrase d'accroche devient automatiquement « Des livres à offrir à Papi, à Mamie, à Papa, à ton frère, à ta sœur, à ta belle-mère, à Maman… ».

## 1. Ajouter les liens Amazon
1. Ouvrir `index.html` dans un éditeur de texte brut (VS Code, Bloc-notes, TextEdit en « texte brut »).
2. En haut du fichier, la **ZONE À MODIFIER** : coller chaque lien entre les guillemets.
   `lienAmazon: "https://www.amazon.fr/dp/XXXXXXXXXX",` (et `lienAmazonRelie` pour l'édition reliée).
3. Enregistrer, recharger : le badge passe de « Bientôt disponible » à « Disponible » et tous les boutons du site pointent vers Amazon.
- Un lien **Amazon Attribution** se colle au même endroit. Un lien sans `https://` est corrigé automatiquement.

## 2. Afficher les vraies couvertures (conseillé)
Placer l'image à côté de `index.html` puis renseigner `couverture: "papi-couverture.png",`. Tant que le champ est vide, une couverture dessinée aux couleurs du livre s'affiche. Pour Papa, Frérot, Sœurette et Belle-Maman, c'est déjà fait.

## 3. À compléter pour « Maman, raconte-moi ton histoire »
`sousTitre`, `motDuLibraire`, `points`, `caracteristiques`, `sommaire`, `extraits`, `description` (texte provisoire), `couleurs` si pas d'image.

## 4. Mettre en ligne (gratuit)
- **Netlify Drop** : glisser le dossier (index.html + images) sur app.netlify.com/drop, puis brancher un nom de domaine si besoin.
- Autres options : GitHub Pages, Cloudflare Pages, ou un hébergeur classique.

## 5. Options de la zone de configuration
| Champ | Effet |
|---|---|
| `metaPixelId` | Active le pixel Meta **après consentement**. Chaque clic vers Amazon envoie l'événement `ClicAmazon` (livre, format). |
| `email`, `instagram`, `pageAuteurAmazon` | Liens ajoutés en bas de page. |
| `mentionsLegales` | Fenêtre « Mentions légales ». À remplir avant la mise en ligne. |
| `delaiLivraisonJours` | Le calendrier ignore les fêtes trop proches pour être livré à temps (7 jours par défaut). |
| `nouveaute` | Pastille « Nouveauté » (actuellement Papi, Papa, Frérot, Sœurette et Belle-Maman). |
| `occasions` | Fêtes associées : `meres`, `peres`, `grands-meres`, `grands-peres`, `freres-soeurs`, `noel`. |
| `motChapitre` | Remplace le mot « Chapitre » : `"Piste"` pour Papa, `"Niveau"` pour Frérot, `"Rubrique"` pour Sœurette, `"Étape"` pour Belle-Maman. |
| `vitrine` | Place du livre dans la vitrine 3D (1 = premier plan, 0 = hors vitrine). |

## 6. Contrôles effectués (version 6)
- Testé dans Chromium (ordinateur 1366 px et mobile 390 px) : aucune erreur JavaScript, aucun défilement horizontal.
- Calendrier vérifié au 3 octobre 2026 : Noël dans 83 jours (« Pour Papi, Mamie, Papa, ton frère, ta sœur, ta belle-mère, Maman »), fête des mères le dimanche 30 mai 2027 « Pour Mamie, ta belle-mère, Maman ». Onglets d'extraits : Papi, Mamie, Papa, ton frère, ta sœur, ta belle-mère.

## 7. Points à vérifier
- Le nom « Le Petit Libraire » est déjà utilisé par une page Facebook : vérifier sa disponibilité (INPI) avant d'investir en publicité.
- Les numéros de page des sommaires viennent des fichiers générés : à contrôler sur les épreuves papier.
- Les exemples manuscrits (Mamie, Papa, Frérot, Sœurette, Belle-Maman) sont inventés pour la démonstration (étiquette « Exemple » visible).
- La pastille « Nouveauté » masque un coin de la couverture dans la vitrine : comportement prévu ; retirer `nouveaute: true` pour l'enlever.
