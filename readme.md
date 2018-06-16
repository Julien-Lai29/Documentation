# Documentation

## Convention BEM(Block Element Modifier)

* B > Block
* E > Element
* M > Modifier

```html
<ul class="mainList mainList--xmas">
<li class="mainList__item"><a href="/home" class="mainList__itemLink mainList__itemLink--isActive">Home</a>
</li>


<li class="mainList__item"><a href="/about" class="mainList__itemLink mainList__itemLink--isActive">About</a>
</li>


<li class="mainList__item"><a href="/works" class="mainList__itemLink mainList__itemLink--isActive">Works</a>
</li>
</ul>
```


```css
.mainList {
  display: flex;
  justify-content: space-between;
  &--xmas {
    background: green;
  }
  &__item {
    list-style:none;
    }
  &__itemLink {
    color: red;
    &--isActive {
      color: white;
    }
  }  
}
```
## Pseudo attributs

Les pseudo attributs `before` et `after` permettent de créer des noeuds HTML en CSS.
Ils sont essentiellement utilisés pour ajouter des ornements, des décorations ... On peut bien entendu faire des animations avec, les positionner par rapport à leur parent (relative / absolute). **ils doivent obligatoirement avoir un `content: ''`**
afin de s'afficher.

```html
<section class="cover">
  <img class="ironman" src="https://www.iconfinder.com/icons/52378/helmet_ironman_ic" alt="">
  <h1 class="cover__mainTitle">Présentation des pseudo-attributs</h1>
</section>
```

```css
.cover {
  background: #FDFDFD;
  padding: 20px;

  &__mainTitle {
    text-align: center;
    font-size: 24px;
    color: green;
    position: relative;


    &::before,
    &::after {
      position:absolute;
      content: '';
      display: block;
      width: 50px;
      height: 50px;
      background: green;
      top: 0;
    }
    &::before {
      left: 0;
    }
    &::after {
      right: 0;

    }
  }
}
```


## REM, EM, &, VW Sizing

### &

### EM

* Relative à la tailler de son parent direct.

```CSS
.cover {
  font-size: 16px;
  &__mainTitle {
    /* 1em = 16px / .8em   */
    font-size: .8em;
  }
}
```





*Le REM est basé sur la taille de la racine (soit la balise <html>) qui, par défaut a une valeur de 16px. Afin d'éviter tout calcul, il est nécessaire  de l'écraser en donnant une base de 10 px soit 62.5%.

*Le REM est intéressant à utiliser si les media-queries employées sont en REM également . Cela vous permettra de garder des proportions égales lorsqu'on va redimensionner la page.

*Ses proportions seront également gardées quand l'utilisateur zoomera dans



### VW(idth) / VH(eight)

* Unités relatives à la taille de votre écran (peu importe la device)
* Attention au VH et à son contenu. 100vh == 100vh quoi qu'il arrive.
* VW : très utilse pour les interfaces fluides.

## Liens utiles : https://github.com/h5bp/Front-end-Developer-Interview-Questions
                 http://cssnext.io/features/ IMPORTANT
* [Caniuse]():


## flexboxgrid

col-xs-(nombre de colonnes) : Mobile

col-md-(nombre de colonnes) : Tablette

col-lg-(nombre de colonnes) : Desktop

ALIGNEMENTS

.start- : à gauche

.center- : au millieu

.end- : à droite

(Plus ou moins)



### Parcel

Pour démarrer :

Dans le terminale :

git clone le repo puis npm install dans parcel

npm start

À vous de jouer !

### CSS dans parcel

Crée un dossier "components" dans styles dans ce dossier il y aura TOUS les fichiers CSS de votre projet puis dans le fichiers "style.scss" écrire /*@import './components/nom_du_fichier_CSS';*/  

L'avantage de "découper" son CSS est plus facile pour éviter de tout casser son CSS chaque partie est independante.

### Installation dépendances pour framework JS dans parcel (React, Preact et VUE)

### React

/* Ajoutez un script de démarrage à package.json

package.json
"scripts": {
  "start": "parcel index.html"
} */

npm install --save react
npm install --save react-dom
npm install --save-dev parcel-bundler

### Preact

npm install --save preact
npm install --save preact-compat
npm install --save-dev parcel-bundler
npm install --save-dev babel-preset-env
npm install --save-dev babel-preset-preact

/* Ensuite, assurez-vous que la configuration Babel suivante est présente.

 .babelrc
{
  "presets": ["env", "preact"]
}
Ajoutez un script de démarrage à package.json

// package.json
"scripts": {
  "start": "parcel index.html"
} */

/* Ajoutez un script de démarrage à package.json

 package.json
"scripts": {
  "start": "parcel index.html"
} */

### VUE

npm install --save vue
npm install --save-dev parcel-bundler


/* Ajoutez un script de démarrage à package.json

 package.json
"scripts": {
  "start": "parcel index.html"
}



## Définition :

Convention : façon de faire du css avec des "règles" et des normes à suivre (nom des classes etc...)

## Keyframes

Définition : La règle @ @keyframes permet aux auteurs de définir les étapes qui composent la séquence d'une animation CSS. Cela permet de contrôler une animation plus finement que ce qu'on pourrait obtenir avec les transitions.

Exemple :


```css
.arrow {
    text-align: center;
    animation-name: floating; /* Nom de l'animation */
    animation-duration: 1.5s;
    animation-iteration-count: infinite;
    animation-timing-function: ease-in-out;
  }
  @keyframes floating { /* Nom de l'animation (pour appeler l'animation dans l'élément')*/
    from {
      transform: translate(0, 0px);
    }

    65% {
      transform: translate(0, 15px);
    }

    to {
      transform: translate(0, -0px);
    }
  }
  ```
