# Langage Javascript

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les `structures` de base du langage  ✔️
- les normes `ecmascript` ❌ / ✔️
- l'utilisation de l'`asynchrone`  ✔️
- les spécifités du mot-clef `this` ❌ / ✔️

## 💻 Je code en Javascript

### Un exemple de code commenté ✔️

```javascript
// State permettant d'initialiser l'état et l'écoute de l'état de l'entité Tags qui est un tableau de tag
  const [selectedTags, setSelectedTags] = useState<number[]>([]);

// Code permettant de cocher ou de décocher des tags selon une série de conditions
  const tagChange = (tagId: number) => {
    // Mise à jour de l'état des tags sélectionnés
    setSelectedTags((prevSelectedTags) => {
      if (prevSelectedTags.includes(tagId)) {
        // Si le tag est déjà sélectionné, le retirer
        return prevSelectedTags.filter((id) => id !== tagId);
      } else {
        // Sinon, l'ajouter à la liste des tags sélectionnés
        return [...prevSelectedTags, tagId];
      }
    });
  };
```
Exemple d'une petite fonction asynchrone :
```
// Enregistrement d'un nouveau tag via un formulaire
  async function onSubmit(e: FormEvent<HTMLFormElement>) {
    const result = await createTag({
      variables: {
        data: {
          name: newTag,
        },
      },
    });
  }
```
### Utilisation dans un projet  ✔️

[https://github.com/LaureJanin/the-good-corner]

Description :

### J'ai utilisé ce langage en production ❌ / ✔️

[lien du projet](...)

Description :

### J'ai utilisé ce langage en environement professionnel ❌ / ✔️

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

