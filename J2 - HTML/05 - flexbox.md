# Introduction au Flex-box

Il y a des propriétés qui s'appliquent au conteneur et d'autre aux éléments contenus. 

Par exemple

- display : flex s'applique au conteneur

- flex : au élément contenu

Deux notions fondamentales sur le conteneur

1. **Axe principal**

Dans le conteneur on a par défaut :

flex-direction : raw par défaut

Dans ce cas l'axe principal est **l'axe horizontal** et **l'axe secondaire vertical**.

2. **Axe secondaire**

Si dans le conteneur 

**flex-direction : column**

Dans ce cas l'axe principal est **l'axe vertical** et **l'axe secondaire horizontal**

- Disposition en ligne

Pour que des div, comme ci-dessous, dans un conteneur flex se mettent sur l'axe horizontal en ligne, vous appliquerez les css qui suivent sur le div.container

```html

<div class="container">
    <div>1</div>
    <div>2</div>
    <div>3</div>
</div>

```

Les CSS

```css
div.container{
    background-color: aqua;
    display : flex;
}
```

Quelques propriétés utiles pour placer les éléments

**Si le conteneur est en display flex raw** ( propriété par défaut )

- **justify-content** permet de placer les éléments sur l'axe horizontal en flex direction raw.

- **align-itmes** permet de positionner sur l'axe vertical. 

Propriétés sur les éléments contenus d'un display flex :

- **align-self** permet d'aligner les éléments contenus sur leur axe secondaire.

- **flex** est une propriété raccourcie qui définit la capacité d'un élément à modifier ses dimensions afin de remplir l'espace disponible de son conteneur. Les propriétés sont (flex-grow, flex-shrink et flex-basis.)

**Exemples :**

/* Deux valeurs : flex-grow | flex-basis */
flex: 1 30px;

/* Deux valeurs : flex-grow | flex-shrink */
/* flex-basis vaut alors 0 */
flex: 2 2;

/* Trois valeurs : flex-grow | flex-shrink | flex-basis */
flex: 2 2 10%;
