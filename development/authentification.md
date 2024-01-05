# Authentification

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris 

- Les 3 phases de l'authentification  ✔️
- La définition d'un JWT (vs Session) ✔️
- L'utilisation des cookies (vs Localstorage)  ✔️

## 🎤 J'explique

### Les 3 phases de l'authentification

3 principes, 3 étapes isolées et différentes

- L’enregistrement (signup) : stockage de l'identité en BDD, hachage du mot de passe (argon2)
- L’identification (signin) : interroge la BDD sur l'identité de l'utilisateur avec comparaison
- L’autorisation (authorization) 

Chaque étape doit être traitée de manière différente avec des choix techniques spécifiques.

### JWT VS Session

**JWT** :

- Format : Un JWT est jeton non falsifiable généré par le serveur avec une signature digitale (jsonwebtoken). Il est généralement constitué de trois parties : l'en-tête (header), la charge utile (payload) et la signature, transformée en base 64.
- Stockage : Les JWT sont généralement stockés côté client, par exemple dans un cookie ou dans le stockage local du navigateur. Ils peuvent également être inclus dans les en-têtes HTTP.
- Durée de vie : Un JWT peut avoir une durée de vie spécifiée, après laquelle il devient invalide. Cela permet de contrôler la validité du jeton.
- Décentralisé : Les JWT peuvent être vérifiés de manière décentralisée par n'importe quelle partie qui possède la clé de signature.

Le **JWT contient des informations en clair**, il n’est pas crypté ni encodé, donc ne pas y mettre d’infos sensible.

**Session** :

- Format : Les sessions sont souvent basées sur un identifiant de session unique stocké côté serveur. 
- Stockage : Les informations de session sont stockées côté serveur. Seul l'identifiant de session est stocké côté client (dans un cookie, généralement).
- Durée de vie : La durée de vie d'une session est généralement déterminée par le serveur. Elle peut être configurée pour expirer après un certain laps de temps d'inactivité.
- Centralisé : La vérification de la session se fait côté serveur, et le serveur maintient l'état global des sessions.
 
### Cookies VS Local Storage

**Cookies** :

- Stockage : Les cookies sont des petits fichiers texte stockés côté client. Ils sont envoyés et reçus avec chaque requête HTTP, ce qui les rend adaptés pour la gestion des sessions et le stockage d'informations côté client.
- Durée de vie : Les cookies peuvent avoir une durée de vie spécifiée, soit par expiration après un certain laps de temps, soit par une date d'expiration spécifique.
- Transmission automatique : Les cookies sont automatiquement inclus dans les en-têtes HTTP pour chaque requête vers le domaine correspondant, ce qui les rend disponibles pour le serveur.

**Local Storage** :

- Stockage : Le local storage est une API JavaScript qui permet de stocker des données en tant que paires clé-valeur directement dans le navigateur du client.
- Durée de vie : Les données stockées dans le local storage restent présentes même après la fermeture du navigateur, et elles ne sont pas soumises à une expiration automatique.
- Transmission automatique : Contrairement aux cookies, les données du localStorage ne sont pas automatiquement incluses dans les requêtes HTTP. 
- Sécurité : Les données du localStorage sont accessibles via JavaScript, ce qui peut représenter un risque de sécurité si elles contiennent des informations sensibles.

