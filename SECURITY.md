# Politique de sécurité

## Signaler une vulnérabilité

Merci de **ne pas ouvrir d'issue publique** pour une faille de sécurité.

Utilise le signalement privé de GitHub : onglet **Security → Report a vulnerability** de ce dépôt. Décris le comportement observé, les étapes pour le reproduire et son impact, **sans joindre de vrai jeton, de vraies données personnelles ni de capture de réseau non expurgée**. Le code source n'étant pas public, une description précise (version de l'application, téléphone, étapes) suffit.

Ce projet est maintenu à titre personnel : je fais de mon mieux pour répondre rapidement, sans engagement de délai.

## Périmètre

Sont concernés, par exemple :

- une fuite de jetons ou de données personnelles (journaux, caches, presse-papiers, notifications) ;
- un contournement du verrouillage de l'écran « Mes informations » ;
- une donnée sensible écrite en clair alors qu'elle devrait être dans le stockage sécurisé ;
- un lien ou un schéma d'URL ouvert sans contrôle ;
- un fichier de configuration importé qui affaiblirait la sécurité ;
- une dépendance avec une faille connue.

Ne sont pas concernés : les failles de l'extranet de l'école ou des services Microsoft (à signaler à leurs propriétaires), et les appareils déjà compromis (débridés, accès administrateur).

## Mesures en place

- Jetons de connexion, résultats et identifiants dans le **stockage sécurisé** du système.
- Mot de passe jamais lu ni enregistré : saisi sur la page de connexion Microsoft.
- Informations personnelles **jamais écrites sur le disque**, protégées par biométrie, effacées en arrière-plan.
- Communications en HTTPS ; liens externes limités à `https`.
- Aucun jeton dans les journaux ; journaux détaillés réservés aux versions de développement.
- Sauvegarde automatique d'Android désactivée pour l'application.
- Presse-papiers vidé automatiquement après la copie d'une donnée sensible, « au mieux » (selon le système).
- Import de configuration validé (types, bornes) ; les réglages de sécurité ne sont ni exportés ni importés.
- Versions Android signées avec une clé unique ; empreintes SHA-256 des fichiers publiées avec chaque release.

## Conseils d'utilisation

- Télécharge l'application **uniquement depuis les releases de ce dépôt** et vérifie les empreintes (voir le [README](README.md)).
- Active le verrouillage d'écran de ton téléphone : il protège le stockage sécurisé et l'écran des informations personnelles.
- Déconnecte-toi avant de prêter, revendre ou désinstaller ton appareil.
