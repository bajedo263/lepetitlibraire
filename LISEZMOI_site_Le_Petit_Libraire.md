# Site « Le Petit Libraire » : mode d'emploi

Landing page qui réunit les livres d'Adèle Mercier sous l'identité « Le Petit Libraire ».
- **Fichiers à héberger** : `index.html` (un seul fichier, polices intégrées, aucun appel à Google Fonts) + `papa-couverture.jpg` + `frere-couverture.jpg` + `soeur-couverture.jpg` + `bellemere-couverture.jpg` + `beaupere-couverture.jpg` + `maman-couverture.jpg`, tous dans le même dossier.
- **Aperçu privé sur claude.ai** : https://claude.ai/artifact/1PycAzFy7CSJpkT1AY1E1y (version 9 du 3 octobre 2026 : « Maman, vide ton sac ! » remplace « Maman, raconte-moi ton histoire »).

## 0. Livres présents (ordre d'affichage)
| Livre | Statut des contenus | Couverture affichée |
|---|---|---|
| Papi, à toi la parole ! | complet (sommaire, 26 extraits, 4 pages exemple) | dessinée (vert sapin) tant que `couverture` est vide |
| Avant d'être Mamie | complet (22 extraits, 3 pages exemple) | dessinée : renseigner `couverture: "mamie-couverture.png"` avec le PNG 1800 × 2700 déjà fourni |
| Papa, face B | complet (sommaire en 12 « pistes », 24 extraits, 3 pages exemple) | vraie couverture : `papa-couverture.jpg` |
| Frérot, mode coop | complet (sommaire en 12 « niveaux », 24 extraits, 3 pages exemple) | vraie couverture : `frere-couverture.jpg` |
| Sœurette, le numéro spécial | complet (sommaire en 12 « rubriques », 24 extraits, 3 pages exemple) | vraie couverture : `soeur-couverture.jpg` |
| Destination Belle-Maman | complet (sommaire en 12 « étapes », 24 extraits, 3 pages exemple) | vraie couverture : `bellemere-couverture.jpg` |
| Beau-Papa, le rôle de sa vie | complet (sommaire en 12 « scènes », 24 extraits, 3 pages exemple) | vraie couverture : `beaupere-couverture.jpg` |
| **Maman, vide ton sac !** *(remplace l'ancienne fiche « Maman, raconte-moi ton histoire », pastille « Nouveauté »)* | complet : sous-titre, mot du libraire, 4 points forts, sommaire en 12 « objets », 24 extraits, 3 pages exemple ; fête des mères, Noël | **vraie couverture** : `maman-couverture.jpg` (640 × 960) |

Ce qui change avec « Maman, vide ton sac ! » (version 9) :
- **Vitrine 3D** : Maman au premier plan (`vitrine: 1`), puis Beau-Papa (2) et Belle-Maman (3). Sœurette sort de la vitrine (`vitrine: 0`) ; remets 1, 2 ou 3 pour l'y replacer.
- **Extraits** : l'onglet « Pour Maman » est désormais rempli (24 questions). Le mot « Chapitre » devient « Objet » (`motChapitre: "Objet"`).
- **Questions au libraire** : Maman ajoutée dans « Faut-il aimer écrire ? », « Quel livre choisir ? » (nouvelle description) et « Quel est le format ? ».
- **Ruban des occasions** : ajout de « Les 60 ans de Maman ».
- **Calendrier** : la fête des mères (dimanche 30 mai 2027) affiche Mamie, ta belle-mère et Maman ; Noël liste les huit destinataires.
- La section « À compléter pour Maman » de l'ancien mode d'emploi n'a plus lieu d'être : tout est rempli.

## 1. Ajouter les liens Amazon
1. Ouvrir `index.html` dans un éditeur de texte brut (VS Code, Bloc-notes, TextEdit en « texte brut »).
2. En haut du fichier, la **ZONE À MODIFIER** : coller chaque lien entre les guillemets.
   `lienAmazon: "https://www.amazon.fr/dp/XXXXXXXXXX",` (et `lienAmazonRelie` pour l'édition reliée).
3. Enregistrer, recharger : le badge passe de « Bientôt disponible » à « Disponible » et tous les boutons du site pointent vers Amazon.
- Un lien **Amazon Attribution** se colle au même endroit. Un lien sans `https://` est corrigé automatiquement.
- **Ancien livre Maman** : si « Maman, raconte-moi ton histoire » reste en vente quelque temps, ne mets pas son lien sur cette fiche. Le site présente uniquement la nouvelle version.

## 2. Afficher les vraies couvertures (conseillé)
Placer l'image à côté de `index.html` puis renseigner `couverture: "papi-couverture.png",`. Tant que le champ est vide, une couverture dessinée aux couleurs du livre s'affiche. Pour Papa, Frérot, Sœurette, Belle-Maman, Beau-Papa et Maman, c'est déjà fait.

## 3. Mettre en ligne (gratuit)
- **Netlify Drop** : glisser le dossier (index.html + images) sur app.netlify.com/drop, puis brancher un nom de domaine si besoin.
- Autres options : GitHub Pages, Cloudflare Pages, ou un hébergeur classique.
- Le fichier `index.html` livré ici est un document HTML complet (doctype, en-tête). La version publiée sur claude.ai est la même, sans cette enveloppe (claude.ai l'ajoute à la publication).

## 4. Options de la zone de configuration
| Champ | Effet |
|---|---|
| `metaPixelId` | Active le pixel Meta **après consentement**. Chaque clic vers Amazon envoie l'événement `ClicAmazon` (livre, format). |
| `email`, `instagram`, `pageAuteurAmazon` | Liens ajoutés en bas de page. |
| `mentionsLegales` | Fenêtre « Mentions légales ». À remplir avant la mise en ligne. |
| `delaiLivraisonJours` | Le calendrier ignore les fêtes trop proches pour être livré à temps (7 jours par défaut). |
| `nouveaute` | Pastille « Nouveauté » (actuellement Papi, Papa, Frérot, Sœurette, Belle-Maman, Beau-Papa et Maman). |
| `occasions` | Fêtes associées : `meres`, `peres`, `grands-meres`, `grands-peres`, `freres-soeurs`, `noel`. |
| `motChapitre` | Remplace le mot « Chapitre » : `"Piste"` pour Papa, `"Niveau"` pour Frérot, `"Rubrique"` pour Sœurette, `"Étape"` pour Belle-Maman, `"Scène"` pour Beau-Papa, `"Objet"` pour Maman. |
| `vitrine` | Place du livre dans la vitrine 3D (1 = premier plan, 0 = hors vitrine). |

## 5. Contrôles effectués (version 9)
- Testé dans Chromium (ordinateur 1366 px et mobile 390 px) : aucune erreur JavaScript, aucun défilement horizontal.
- Vitrine : Maman au premier plan avec sa vraie couverture, puis Beau-Papa et Belle-Maman. Fiche Maman : sous-titre, mot du libraire manuscrit, 4 points forts, caractéristiques, sommaire en 12 objets.
- Phrase d'accroche générée : « Des livres à offrir à Papi, à Mamie, à Papa, à ton frère, à ta sœur, à ta belle-mère, à ton beau-père, à Maman… ».

## 6. Points à vérifier
- Le nom « Le Petit Libraire » est déjà utilisé par une page Facebook : vérifier sa disponibilité (INPI) avant d'investir en publicité.
- Les numéros de page des sommaires viennent des fichiers générés : à contrôler sur les épreuves papier.
- Les exemples manuscrits (Mamie, Papa, Frérot, Sœurette, Belle-Maman, Beau-Papa, Maman) sont inventés pour la démonstration (étiquette « Exemple » visible).
- Le livre Beau-Papa figurait déjà sur le site publié : je l'ai conservé tel quel. Ses fichiers (livre, campagne) ne sont pas dans le projet AMAZON KDP ; pense à les y ajouter s'ils existent ailleurs.
