# Auto-Blog – Interface de blog headless automatisée ( Cloudflare/Make/Airtable )

Bienvenue sur **Auto-Blog**, une interface de blog dynamique, légère et moderne, entièrement automatisée. Ce projet combine une page web statique unique (`blog.html`) avec une pipeline d'automatisation qui récupère, stocke et affiche des articles sans aucune intervention manuelle.

---

## ✨ Aperçu

Auto-Blog est conçu comme une **application monopage (SPA)** qui s'appuie sur une architecture headless. Les articles sont automatiquement collectés via **Make (ex-Integromat)** , stockés dans **Airtable**, puis servis par une **API Cloudflare Worker** pour être affichés en temps réel sur le blog.

---

## 🔄 Flux de données automatisé

Make (scénarios) → Airtable (base de données) → Cloudflare Worker (API) → blog.html (front-end)


1. **Make** récupère périodiquement des articles depuis diverses sources (RSS, scraping, autres APIs).
2. **Airtable** stocke les articles avec leurs métadonnées (titre, contenu, date, slug, langue).
3. **Cloudflare Worker** interroge Airtable et expose une API REST propre pour le front-end.
4. **blog.html** appelle cette API et affiche les articles dynamiquement.

---

## 🛠️ Architecture technique

### Front-end (SPA statique)
- Fichier unique `blog.html` (HTML, CSS, JavaScript vanilla)
- Routage côté client via `pushState` pour des URLs uniques par article
- Support multilingue (fr/en) intégré
- Design responsive sans framework externe

### Back-end headless
- **API** : Cloudflare Worker (JavaScript) – endpoint configurable
- **Base de données** : Airtable (structure simple : titres, contenus, dates, slugs)
- **Automatisation** : Make (scénarios planifiés pour l'import d'articles)

---

## ✨ Fonctionnalités

- **Affichage liste/articles** : Récupération automatique des derniers articles depuis l'API
- **Consultation détaillée** : Affichage d'un article complet via URL paramétrée (`?id=...&slug=...`)
- **Navigation fluide** : Chargement AJAX sans rechargement de page
- **Bouton de retour** : Navigation intuitive entre liste et article
- **Multilingue** : Interface et dates localisées (français/anglais)
- **Responsive** : Adaptation mobile/tablette/desktop
- **Indicateurs de chargement** : Feedback utilisateur pendant les appels API
- **Mise à jour automatique** : Les nouveaux articles apparaissent dès leur import par Make

---

## 🗂️ Structure du projet

auto-blog/
├── blog.html # Application monopage complète
├── Make scenarios/ # (hors dépôt) Scénarios d'automatisation
├── Airtable base/ # (hors dépôt) Structure de la base
└── Cloudflare Worker/ # (hors dépôt) Code de l'API
