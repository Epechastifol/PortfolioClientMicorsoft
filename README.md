# Microsoft — Site de formation et consultance

Site statique présentant des formations et services de consultance en Excel, Power BI et VBA.

## Contenu du dépôt
- `index.html` — page d'accueil
- `formation-excel.html`, `formation-powerbi.html` — pages de formation
- `consultance-excel.html`, `consultance-powerbi.html` — pages de consultance
- `contenu-modeles.html`, `contenu-guide.html`, `contenu-tutos.html` — ressources gratuites
- `contact.html` — formulaire de contact (configuré pour Netlify Forms)
- `thank-you.html` — page de remerciement après soumission du formulaire
- `assets/` — CSS, JS, images et documents

## Objectif
Ce site bilingue/français est une vitrine pour des formations et services professionnels autour de la data (Excel, Power BI, automatisation VBA). Il est prévu pour être déployé en tant que site statique (ex. Netlify).

## Déploiement (Netlify)
1. Créez un nouveau site sur Netlify en liant ce dépôt Git.
2. Configuration par défaut (build command vide, publish directory racine `/`).
3. Le formulaire de contact est configuré pour Netlify Forms (champ `form-name`, honeypot, `data-netlify="true"`). Après déploiement, les envois apparaîtront dans l'interface Netlify.

Tester localement avec Netlify CLI:

```powershell
# installer netlify-cli si nécessaire
npm install -g netlify-cli
# lancer le serveur local (dans le dossier du projet)
netlify dev
```
Soumettez le formulaire via `contact.html` et vérifiez les requêtes dans la console Netlify Dev.

## Structure et bonnes pratiques
- Tous les assets (CSS, JS, images) se trouvent sous `assets/`.
- Utiliser les pages modèles (`formation-*.html`, `consultance-*.html`) pour ajouter ou harmoniser le contenu.
- Styles centralisés dans `assets/css/styles.css`.

## Licence
Ce projet est distribué sous licence MIT — voir `LICENSE`.

## Auteur / Contact
IGNAGALI ZIAKRABA KALZILKI — ignagalizk@gmail.com

---

Vous pouvez me demander d'ajouter un script de build minimal, un workflow GitHub Actions, ou que je prépare un commit prêt à déployer sur Netlify.