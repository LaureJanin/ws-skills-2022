# REST API

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les verbes HTTP  ✔️, je connais et je n'ai utilisé que les principaux : get, post, put, delete, patch.
- les statuts HTTP  ✔️, je ne connais que les principaux (100, 200, 201, 202, 204, 301, 404, 401, 500, 501, 504)
- les endpoints  ✔️
- CORS ❌ / ✔️
- la nomenclature recommandée pour les routes  ✔️

## 💻 J'utilise

### Un exemple personnel commenté  ✔️

Exemple dans un projets de routes :
```
// Routes log
router.post("/login", adminControllers.log);
router.post("/register", adminControllers.add);

// Middleware called before the route handler function to verify whether the user is authenticated.
router.use(authenticateToken);

// Routes admin
router.get("/admin", adminControllers.browse);
router.get("/admin/:id", adminControllers.read);
router.delete("/admin/:id", adminControllers.destroy);

// Routes borrower
router.get("/borrower", borrowerControllers.browse);
router.get("/borrower/:id", borrowerControllers.read);
router.put("/borrower/:id", borrowerControllers.edit);
router.post("/borrower", borrowerControllers.add);
router.delete("/borrower/:id", borrowerControllers.destroy);

// Routes book
// All books
router.get("/books", bookControllers.browse);
// Book of the admin
router.get("/book/:id", bookControllers.readAdmin);
// Book by id
router.get("/onebook/:id", bookControllers.read);
router.put("/book/:id", bookControllers.edit);
router.post("/book", bookControllers.add);
router.delete("/book/:id", bookControllers.destroy);
```

### Utilisation dans un projet ❌ / ✔️

[(https://github.com/LaureJanin/checkpoint4_qui-a-mon-livre)]

Description :

Il s'agit d'une bibliothèque de livres empruntés. Elle permet d'enregistrer les livres que nos amis, notre famille ou nos collègues nous ont empruntés, de noter la date et un moyen de les joindre.

### Utilisation en production si applicable❌ / ✔️

[https://www.qui-a-mon-livre.fr/]

Description :

### Utilisation en environement professionnel ❌ / ✔️

Description :

## 🌐 J'utilise des ressources

### Titre

- lien
- description

## 🚧 Je franchis les obstacles

### Point de blocage ❌ / ✔️

Description:

Plan d'action : (à valider par le formateur)

- action 1 ❌ / ✔️
- action 2 ❌ / ✔️
- ...

Résolution :

## 📽️ J'en fais la démonstration

- J'ai ecrit un [tutoriel](...) ❌ / ✔️
- J'ai fait une [présentation](...) ❌ / ✔️
