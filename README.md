# Auto-Blog - Interface de Blog Headless

Bienvenue sur **Auto-Blog**, une interface de blog dynamique, légère et moderne. Ce projet est une page web statique unique (`blog.html`) qui agit comme un client pour une API distante, affichant et gérant des articles de blog de manière fluide.

## ✨ Aperçu

Auto-Blog est conçu comme une **application monopage (SPA)**. Il offre une expérience de navigation rapide et interactive, sans rechargement de page, en s'appuyant sur du JavaScript moderne et une architecture découplée.

## 🛠️ Comment ça fonctionne ?

Le cœur du projet repose sur trois éléments :

1.  **Front-end Statique** : Le fichier `blog.html` contient toute la structure, le style et la logique de l'interface. Il est hébergeable n'importe où (GitHub Pages, Netlify, serveur classique).
2.  **API Back-end (Headless)** : L'application se connecte à un Worker Cloudflare (`blog-airtable.mitshi.workers.dev`) qui fait office d'API. Ce worker récupère les articles depuis une base de données (probablement Airtable).
3.  **Routage Dynamique** : La navigation est gérée en JavaScript. L'URL change via `pushState` pour refléter l'article consulté (ex: `blog.html?id=123&slug=mon-article&lang=fr`), mais la page ne se recharge pas.

## 🚀 Fonctionnalités

*   **Affichage de la liste des articles** : Récupère et affiche les titres, extraits et dates depuis l'API.
*   **Consultation d'un article détaillé** : Affiche le contenu complet d'un article en fonction des paramètres `id` et `slug` dans l'URL.
*   **Navigation fluide** : Charge le contenu dynamiquement sans rechargement de page (AJAX).
*   **Bouton de retour fonctionnel** : Permet de revenir à la liste des articles sans perdre l'état de l'application.
*   **Support multilingue intégré** : Change la langue de l'interface et le format des dates via le paramètre `lang` (fr/en).
*   **Design responsive et moderne** : S'adapte aux mobiles et tablettes avec une interface épurée et des interactions au survol.
*   **Gestion des erreurs et chargement** : Affiche des messages appropriés pendant le chargement ou en cas d'erreur réseau.

## 📁 Structure du projet

Le projet se compose d'un seul fichier :

Auto-Blog/
└── blog.html # L'application de blog complète (HTML, CSS, JS)



## ⚙️ Installation et utilisation

1.  **Téléchargez** le fichier `blog.html`.
2.  **Hébergez-le** sur n'importe quel serveur web statique (ou même en local).
3.  **Accédez-y** via votre navigateur.

L'application est immédiatement fonctionnelle, à condition que le Worker Cloudflare (`https://blog-airtable.workers.dev`) soit en ligne et accessible.

## 🧩 Personnalisation

Vous pouvez adapter ce blog à vos propres besoins :

*   **Changer la source de données** : Modifiez la constante `BLOG_WORKER_URL` dans le JavaScript pour pointer vers votre propre API.
*   **Modifier le design** : Adaptez le style CSS dans la balise `<style>` pour l'accorder à votre charte graphique.
*   **Ajouter des langues** : Étendez l'objet `translations` pour supporter de nouvelles langues.

## ☁️ Dépendance

La seule dépendance de ce projet est l'API back-end. Assurez-vous que l'URL du Worker Cloudflare est correcte et que le service est opérationnel pour que le blog fonctionne.
