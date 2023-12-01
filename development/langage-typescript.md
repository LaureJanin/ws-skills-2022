# TypeScript

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- l'intéret de TypeScript dans l'IDE  ✔️
- les types de bases  ✔️
- comment et pourquoi étendre une interface ❌ / ✔️
- les classes et les decorators  ✔️

## 💻 J'utilise

### Un exemple personnel commenté  ✔️
Voici un composent AdCard.
Il reçoit de son composent parent une série de props.
Ces props sont typées avec TS : AdCardType.
AdCardType contient le type AdType + une fonction onDelete.
```
export type AdType = {
  id: number;
  title: string;
  description: string;
  owner: string;
  price: number;
  imgUrl: string;
  location: string;
  createdAt: string;
  category: string;
  tags: {
    id: number;
    name: string;
  }[];
  link: string;
};

export type AdCardProps = AdType & {
  onDelete?: () => void;
};

const AdCard = (props: AdCardProps): React.ReactNode => {
  return (
    <div className="ad-card-container" key={props.id}>
      <a className="ad-card-link" href={props.link}>
        <img className="ad-card-image" src={props.imgUrl} />
        <div className="ad-card-text">
          <div className="ad-card-title">{props.title}</div>
          <div className="ad-card-price">{props.price} €</div>
        </div>
      </a>
      {props.onDelete && <button className="button">Supprimer</button>}
    </div>
  );
};
```

### Utilisation dans un projet  ✔️

[lien github](...)

Description :

### Utilisation en production si applicable❌ / ✔️

[https://github.com/LaureJanin/the-good-corner]

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
