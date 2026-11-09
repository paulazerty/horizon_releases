# Politique de confidentialité

*Dernière mise à jour : voir l'historique du fichier sur GitHub.*

HORIZON est un **projet personnel et non officiel**. Elle n'a aucun serveur : **l'auteur ne reçoit, ne collecte et ne conserve aucune donnée d'utilisateur.** Tout se passe sur ton appareil.

## En résumé

- Aucun compte, aucune publicité, aucune statistique d'usage, aucun rapport d'erreurs automatique, aucun traceur.
- Les données affichées proviennent de **ton propre compte** sur l'extranet de l'école ; elles sont conservées **uniquement sur ton appareil**.
- Se déconnecter dans l'application supprime tes données locales.

## Données conservées sur l'appareil

| Donnée | Où | Protection | Suppression |
|---|---|---|---|
| Jetons de connexion (accès, rafraîchissement) et identifiant du client | Stockage sécurisé du système (Keychain iOS, Keystore Android) | Chiffrement du système | Déconnexion |
| Résultats d'évaluations | Stockage sécurisé | Chiffrement du système | Déconnexion |
| Identifiants des outils de l'école (mots de passe initiaux) | Stockage sécurisé | Chiffrement du système | Déconnexion |
| Planning : blocs, salles, formateurs et leurs adresses professionnelles | Préférences de l'application | Espace privé de l'application | Déconnexion |
| Contacts (noms, adresses, photos), outils (liens, logos), listes de choix, liste des documents, photo de profil | Fichiers de l'application | Espace privé de l'application | Déconnexion |
| Documents PDF téléchargés | Dossier de l'application | Espace privé de l'application | Déconnexion, ou suppression depuis l'écran Documents |
| Cookies de la page de connexion Microsoft (session ouverte, utilisée pour renouveler la connexion sans ressaisir tes identifiants) | Stockage de la WebView du système | Espace privé de l'application | Déconnexion |
| Informations personnelles (identité, adresse, numéro de sécurité sociale, etc.) | **Jamais enregistrées** : mémoire seulement | Biométrie ou code de l'appareil ; effacées en quittant l'application | Automatique |
| Réglages de personnalisation | Préférences de l'application | Espace privé | Réinitialisation ou désinstallation |
| État technique : connecté ou non, heure de connexion, dernière vérification de version, dernières alertes de changement de planning, empreintes des notes déjà notifiées | Préférences de l'application | Espace privé | Alertes : fermeture ou déconnexion ; le reste : désinstallation |

Les contacts, formateurs et délégués apparaissent tels que l'extranet les affiche ; ils ne sont ni partagés ni copiés ailleurs que sur ton appareil.

La sauvegarde automatique d'Android est **désactivée** pour l'application : ces données ne sont pas copiées dans la sauvegarde Google de ton téléphone.

## Données qui quittent l'appareil

Uniquement sur ton action ou pour le fonctionnement normal de l'application :

1. **L'extranet de l'école** : l'application interroge les mêmes services que le site, avec ton jeton de connexion. Ces échanges relèvent de la politique de confidentialité de l'école.
2. **Microsoft** : la connexion se fait sur la page officielle de connexion, affichée dans l'application. Ton mot de passe est saisi sur cette page et **n'est jamais lu ni enregistré par l'application**. Pour renouveler ta session sans te redemander tes identifiants, l'application peut charger cette page dans une **fenêtre invisible** et réutiliser la session Microsoft déjà ouverte ; ce renouvellement automatique se désactive dans *Personnalisation → Sécurité*.
3. **GitHub** : pour vérifier la présence d'une nouvelle version, l'application interroge l'interface publique de GitHub (au plus une fois par jour). GitHub voit alors ton adresse IP, comme pour toute requête. Cette vérification se désactive dans *Personnalisation → Mises à jour de l'application*.
4. **Liens ouverts à ta demande** (Teams, Outlook, SharePoint, formulaire du site, page GitHub) : ils s'ouvrent dans le navigateur ou l'application concernée, soumis à leur propre politique.
5. **Partage d'un fichier de configuration** : si tu exportes ta personnalisation, le fichier ne contient que des réglages d'affichage et de notifications (jamais de donnée personnelle ni de réglage de sécurité). Tu choisis où l'envoyer.

Aucun service de notification à distance n'est utilisé : les notifications sont **fabriquées sur l'appareil**.

## Autorisations demandées

| Autorisation | Finalité |
|---|---|
| Internet / état du réseau | Interroger l'extranet ; détecter le Wi-Fi pour le téléchargement des documents |
| Notifications | Rappels et alertes |
| Démarrage de l'appareil (Android) | Reprogrammer les rappels après un redémarrage |
| Vibreur (Android) | Notifications |
| Biométrie / Face ID | Protéger l'écran des informations personnelles |

L'application ne demande **aucun accès** aux photos, à la musique, aux contacts, à la localisation, à l'appareil photo ou au micro.

## Sécurité

Voir [SECURITY.md](SECURITY.md). Les journaux détaillés n'existent que dans les versions de développement ; ils n'incluent jamais de jeton ni de donnée personnelle.

## Supprimer tes données

- **Se déconnecter** (*Profil → Compte*) supprime jetons, caches, PDF, photo, rappels programmés et session Microsoft de l'application.
- **Désinstaller** l'application supprime le reste. Sur iPhone, certains éléments du Keychain peuvent subsister après une désinstallation : **déconnecte-toi avant de désinstaller**.

## Tes droits

Les données affichées sont celles de ton dossier à l'école. Pour les consulter, les rectifier ou les supprimer à la source, adresse-toi à l'école (son extranet propose d'ailleurs le formulaire de modification). L'application n'en conserve aucune copie ailleurs que sur ton appareil et ne les transmet à personne.

## Contact et modifications

Questions sur ce document : ouvre une issue **sans y mettre de donnée personnelle**. Toute modification de cette politique est visible dans l'historique du fichier et mentionnée dans [CHANGELOG.md](CHANGELOG.md).
