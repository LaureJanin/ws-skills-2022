# GraphQL

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- la différence entre REST et GraphQL ✔️
- les besoins auxquels répond GraphQL ✔️
- la définition d'un schéma ✔️
- Query  ✔️
- Mutation  ✔️
- Subscription ❌ / ✔️

## 💻 J'utilise

### Un exemple personnel commenté  ✔️
Voici une entité nommée "catégory".
Ce code définit deux types d'entrée GraphQL (CategoryCreateInput et CategoryUpdateInput). 
Il utilise le framework TypeORM pour la gestion des entités et des relations avec la base de données et TypeGraphQL pour la définition des types GraphQL

```
@Entity()
@ObjectType()
export class Category extends BaseEntity {
  @PrimaryGeneratedColumn()
  @Field(() => ID)
  id!: number;

  @Column({ length: 100 })
  @Length(3, 100)
  @Field()
  name!: string;

  @OneToMany(() => Ad, (ad) => ad.category)
  @Field(() => [Ad], { nullable: true })
  ads!: Ad[];
}

@InputType()
export class CategoryCreateInput {
  @Field()
  name!: string;
}

@InputType()
export class CategoryUpdateInput {
  @Field({ nullable: true })
  name!: string;
}

```
Ce code déclare un resolver (CategoriesResolver) pour l'entité Category. 
Les resolvers sont utilisés dans les serveurs GraphQL pour définir la logique de récupération et de modification des données. 
Ici la première query récupère toutes les catégories et la deuxième une catégorie par l'ID. 
La mutation permet de créer une catégorie. 

```
@Resolver(Category)
export class CategoriesResolver {
  @Query(() => [Category])
  async allCategories(): Promise<Category[]> {
    const categories = await Category.find({ relations: { ads: true } });
    return categories;
  }

  @Query(() => Category, { nullable: true })
  async category(@Arg("id", () => ID) id: number): Promise<Category | null> {
    const category = await Category.findOne({
      where: { id: id },
      relations: { ads: true },
    });
    return category;
  }

  @Mutation(() => Category)
  async createCategory(
    @Arg("data", () => CategoryCreateInput) data: CategoryCreateInput
  ): Promise<Category> {
    const newCategory = new Category();
    Object.assign(newCategory, data);

    const errors = await validate(newCategory);
    if (errors.length === 0) {
      await newCategory.save();
      return newCategory;
    } else {
      throw new Error(`Error occured: ${JSON.stringify(errors)}`);
    }
  }
}
```

### Utilisation dans un projet ❌ / ✔️

[(https://github.com/LaureJanin/the-good-corner)]

Description :

### Utilisation en production si applicable❌ / ✔️

[lien du projet](...)

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
