# HORIZON

Application mobile **Android et iOS** qui rassemble, sur ton téléphone, les informations de l'extranet de ton école : prochains blocs de cours, calendrier, résultats d'évaluations, contacts, documents, notifications de changement de planning…

Elle fonctionne **entièrement en local** : aucun serveur intermédiaire, aucun compte à créer, aucun suivi.

> **Projet personnel, non officiel.** HORIZON n'est ni éditée, ni approuvée, ni soutenue par l'école dont elle consulte l'extranet. Les noms et marques cités appartiennent à leurs propriétaires. L'extranet peut changer à tout moment et rendre certaines fonctions inopérantes. L'application est fournie « en l'état », sans garantie (voir [LICENSE](LICENSE)). Assure-toi que ton usage respecte la charte informatique de ton établissement.

**Ce dépôt ne contient pas le code source.** Il regroupe la documentation et les versions téléchargeables, dans l'onglet [Releases](../../releases).

## Sommaire

- [Compatibilité](#compatibilité)
- [Fonctionnalités](#fonctionnalités)
- [Installer sur Android](#installer-sur-android)
- [Installer sur iPhone (AltStore ou SideStore)](#installer-sur-iphone-altstore-ou-sidestore)
- [Vérifier l'authenticité des fichiers](#vérifier-lauthenticité-des-fichiers)
- [Première utilisation](#première-utilisation)
- [Notifications et arrière-plan](#notifications-et-arrière-plan)
- [Confidentialité et sécurité](#confidentialité-et-sécurité)
- [Mises à jour](#mises-à-jour)
- [Questions fréquentes](#questions-fréquentes)
- [Signaler un problème](#signaler-un-problème)
- [Licence](#licence)

## Compatibilité

HORIZON ne fonctionne qu'avec **l'extranet de l'école ENI** et ton propre compte d'apprenant. Elle n'a aucun intérêt sans ce compte.

| Plateforme | État |
|---|---|
| Android | Testée sur un téléphone physique (APK dans les Releases) |
| iOS | Testée **sur simulateur uniquement** ; fichier `.ipa` non signé, à installer avec AltStore ou SideStore |

## Fonctionnalités

- **Planning** : prochains blocs de cours (pensé pour l'alternance : les semaines en entreprise sont ignorées), calendrier regroupé par mois, salles, formateurs et interventions.
- **Résultats EPCF** avec tri et filtres, dernières notes sur l'accueil.
- **Mon espace** : contacts avec photos, formateurs, documents PDF lisibles hors ligne, informations personnelles en lecture seule (protégées par la biométrie), identifiants des outils, raccourcis vers les outils de l'école.
- **Notifications** : rappels la veille et le matin d'un bloc, avant les interventions, alerte quand un cours change (formateur, salle, interventions, dates), nouvelles notes.
- **Session** : connexion par la page officielle de connexion Microsoft, renouvellement automatique et discret de la session.
- **Personnalisation poussée** : thème, couleur, taille du texte, mode compact, barre du bas réordonnable, sections de l'accueil réordonnables, export et import de ta configuration.

## Installer sur Android

1. Ouvre la page [Releases](../../releases) et télécharge `horizon-X.Y.Z.apk` de la **dernière version**.
2. (Recommandé) [Vérifie son authenticité](#vérifier-lauthenticité-des-fichiers).
3. Ouvre le fichier. Android demande d'autoriser l'installation depuis cette source (navigateur ou gestionnaire de fichiers) : autorise-la.
4. Si Google Play Protect signale une « application non reconnue » (l'application n'est pas distribuée par le Play Store), choisis *Installer quand même*.
5. Ouvre HORIZON et suis la [première utilisation](#première-utilisation).

**Mettre à jour** : installe simplement le nouvel APK par-dessus l'ancien. Toutes les versions sont signées avec la même clé : tes données sont conservées.

## Installer sur iPhone (AltStore ou SideStore)

Apple n'autorise pas l'installation d'applications hors App Store sans passer par ses outils de développement. Le fichier `horizon-X.Y.Z.ipa` est **non signé** : un outil de « sideloading » le signe avec **ton propre identifiant Apple** au moment de l'installation.

Deux outils courants (suis leur documentation officielle, qui évolue) :

- **AltStore** : <https://altstore.io> (nécessite l'application AltServer sur un Mac ou un PC, sur le même réseau Wi-Fi que l'iPhone, pour installer et renouveler les applications).
- **SideStore** : <https://sidestore.io> (fonctionne sans ordinateur après une configuration initiale).

Principe général :

1. Installe AltStore ou SideStore sur l'iPhone et connecte-le avec ton identifiant Apple.
2. Télécharge `horizon-X.Y.Z.ipa` depuis les [Releases](../../releases) **sur l'iPhone**.
3. Dans AltStore ou SideStore, ajoute le fichier (bouton « + », ou partage du fichier vers l'application) et laisse l'outil l'installer.
4. Si iOS le demande, fais confiance au profil dans *Réglages → Général → VPN et gestion de l'appareil*.
5. Ouvre HORIZON ; autorise les notifications et Face ID quand le système le demande.

À savoir, ce sont des règles d'Apple pour les comptes gratuits :

- l'application **expire au bout de 7 jours** et doit être **renouvelée** (c'est le rôle d'AltStore et de SideStore) ;
- le nombre d'applications installées de cette façon est **limité** ;
- HORIZON n'a été testée que sur simulateur : signale-moi tout comportement inattendu sur iPhone réel.

## Vérifier l'authenticité des fichiers

N'installe HORIZON que depuis **ce dépôt**. Chaque release contient un fichier `SHA256SUMS.txt` et affiche les empreintes dans ses notes.

**Empreinte du fichier** :

```bash
shasum -a 256 horizon-X.Y.Z.apk      # macOS / Linux
certutil -hashfile horizon-X.Y.Z.apk SHA256   # Windows
```

Elle doit correspondre à celle du fichier `SHA256SUMS.txt`.

**Certificat de signature Android** (avec les outils Android SDK) :

```bash
apksigner verify --print-certs horizon-X.Y.Z.apk
```

L'empreinte SHA-256 du certificat doit être :

```
29414fec33fdb05e168ac7c1492c56baaac7a604fa30c00f2547b756440f4e5f
```

Si elle diffère, **n'installe pas** le fichier.

## Première utilisation

1. À l'ouverture, touche **Se connecter** : la page de connexion Microsoft de l'école s'affiche (identifiants et double authentification).
2. L'application charge ton planning, tes résultats, tes contacts, etc.
3. Dans **Profil → Personnalisation**, règle l'apparence, les notifications et la fréquence des mises à jour.
4. Autorise les notifications quand le système le demande.

## Notifications et arrière-plan

- Les **rappels** (veille, matin, interventions) sont programmés d'avance : ils fonctionnent sans connexion.
- La **détection de changement de cours** et la **vérification des notes** nécessitent une connexion valide. L'application renouvelle la session toute seule, d'abord avec un jeton valable 24 h, puis de façon discrète en réutilisant la session Microsoft déjà ouverte sur ton téléphone. Si celle-ci a expiré (durée fixée par Microsoft et l'école), une notification « Reconnecte-toi » t'en avertit.
- **Android** : tâche périodique du système (toutes les 6, 12 ou 24 h, réglable). Selon le constructeur, autorise l'application à fonctionner en arrière-plan (sur Samsung : *Batterie → Sans restriction*).
- **iOS** : iOS ne permet pas de tâche d'arrière-plan fiable pour ce besoin. La détection a lieu à chaque ouverture ; les rappels fonctionnent normalement. Une notification n'apparaît pas pendant que l'application est ouverte : une bannière la remplace.

## Confidentialité et sécurité

- **Aucune donnée n'est envoyée à l'auteur ni à un tiers.** Pas de statistiques, de publicité ni de rapport d'erreurs automatique.
- Jetons, résultats et identifiants sont dans le **stockage sécurisé** du système (Keychain, Keystore).
- Les **informations personnelles** ne sont **jamais enregistrées** : mémoire seulement, protégées par la biométrie, effacées en quittant l'application.
- **Se déconnecter** supprime les données locales, les PDF, la photo, les rappels et la session Microsoft de l'application.

Détails : [PRIVACY.md](PRIVACY.md). Signaler une faille : [SECURITY.md](SECURITY.md).

## Mises à jour

HORIZON vérifie, au plus une fois par jour, s'il existe une version plus récente dans les [Releases](../../releases) de ce dépôt, et te prévient par notification (désactivable dans *Personnalisation → Mises à jour de l'application*). **L'installation reste manuelle** : télécharge le nouveau fichier et installe-le comme la première fois.

L'historique des versions est dans [CHANGELOG.md](CHANGELOG.md). Les numéros suivent le format `MAJEUR.MINEUR.CORRECTIF`.

## Questions fréquentes

**Pourquoi Android affiche-t-il un avertissement à l'installation ?**
Parce que l'application ne vient pas du Play Store. Vérifie les empreintes puis installe-la si elles correspondent.

**Pourquoi dois-je parfois me reconnecter ?**
Quand la session Microsoft de l'école a expiré. L'application renouvelle la session toute seule tant que c'est possible ; sinon, elle te le signale (bandeau « Session expirée » ou notification). Tes données restent consultables hors ligne.

**Pourquoi n'ai-je pas de notification de changement de cours quand je n'ouvre jamais l'application ?**
La vérification en arrière-plan fonctionne sur Android, sous réserve des réglages de batterie du téléphone. Sur iPhone, elle n'a lieu qu'à l'ouverture.

**L'application iPhone cesse de fonctionner au bout d'une semaine.**
C'est la limite des comptes Apple gratuits : renouvelle l'application avec AltStore ou SideStore.

**Puis-je sauvegarder ma personnalisation ?**
Oui : *Personnalisation → Sauvegarde et réinitialisation → Exporter* produit un fichier `.json` sans aucune donnée personnelle, que tu peux importer sur un autre téléphone.

## Signaler un problème

Ouvre une [issue](../../issues) en décrivant le problème, la version (*Profil → À propos*) et ton téléphone.

**N'y joins jamais de donnée personnelle** : noms, notes, e-mails, jetons, captures montrant tes informations. Pour une faille de sécurité, suis [SECURITY.md](SECURITY.md) plutôt que d'ouvrir une issue publique.

## Licence

Voir [LICENSE](LICENSE). Les composants open source inclus conservent leurs propres licences, consultables dans l'application (*Profil → À propos → Licences open source*).
