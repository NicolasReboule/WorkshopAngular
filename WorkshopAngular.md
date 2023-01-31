<div align=center>

![My Skills](https://skillicons.dev/icons?i=angular)

# Workshop Angular
    

</div>
<br>

### Bonjour dans ce workshop vous allez faire vos premiers pas avec le [framework](https://fr.wikipedia.org/wiki/Framework) [Angular](https://angular.io).
### Pour cela vous aurez besoin de [NodeJS](https://nodejs.org/en/).
### Evidemment, vous devrez faire de l'[html](https://www.w3schools.com/html/) et du [css](https://www.w3schools.com/css/).
<br>

---
<br>

## Qu'est ce qu'un *framework* et pourquoi en utiliser un ?</h2>
<br>

### Traduit littéralement, un *framework* est un cadre de travail. Les *frameworks* proposent divers outils aux développeurs, permettant d'accélerer et de faciliter le développement.

<br>

---
<br>

## Comment fonctionne Angular ?</h2>
<br>

### Angular est un framework pour créer des applications web, il est basé sur un système de composants.
<br>

### Contrairement à d'autre framework, Angular utilise le [typescript](https://www.typescriptlang.org), un language de programmation basé sur le javascript mais implémentant le typage.
<br>

### Comme je le disais plus tôt, Angular est basé sur des composants, chacun composé de:
<br>
<ul>
<li>Un fichier .html pour la structure du composant</li>
<li>Un fichier .css pour le design du composant</li>
<li>Un fichier .ts pour le comportement du composant</li>
<li>Un fichier .spec.ts pour faire des units test du composant</li>
</ul>
<br>

### Par exemple, un composant **navBar**:
<br>

![component exemple](/assets/component.png)

<br>

### Les composants sont indépendants, modulables et réutilisables ce qui permet de gagner du temps et de faire moins de code.
### Vous pouvez aussi imbriquer des composants dans d'autres composants pour faire des composants plus complexes.
<br>

### Si vous allez dans le *.ts* d'un composant vous verrez:
<br>

![compoenent ts](/assets/ts_composant.png)

<br>

### *selector* est le nom de la balise html de votre composant
### *templateUrl* est le chemin vers le fichier html de votre composant
### Et *styleUrls* sont les chemins vers les fichiers de style de votre composant
<br>

### Vous pouvez modifier ces éléments comme vous le voulez mais faites **attention de comprendre ce que vous faites** et de ne pas tout casser.
<br>

```ts

export class NavBarComponent {

}

```
<br>

### Ceci est l'endroit dans lequel vous metterez vos fonctions et variables en typescript.

<br>

---
<br>

## Getting Started
<br>

### Vous devrez tout d'abord installer l'invite de commande d'Angular avec la commande:
<br>

```

npm install -g @angular/cli

```

### Une fois installer vous pourrez créer votre premier projet Angular avec la commande:

<br>

```

ng new {{YourProjectName}}

```

### Lors de la création de votre projet on vous demandera:
<br>

![Angular routing](/assets/add_routing.png)
<br>
et

![StyleSheets](/assets/stylesheet.png)

<br>

### Dans notre cas ce sera *Yes* et *CSS*.
<br>

### Une fois l'installation terminée, un dossier avec le nom de votre projet aura été créé.
### Le projet est prêt et vous pouvez le tester en allant dans ce dernier et en utilisant la commande:

<br>

```

ng serve -o

```
<br>

### Si tout fonctionne, vous devriez voir une page générée par défaut par Angular.

<br>

----

<br>

## Comment ça marche ?
<br>

### Dans le dossier que nous venons de créer ce qui nous intéresse est le dossier *app*  se trouvant dans *src*.
<br>

![app folder](/assets/app_folder.png)

<br>

### Dans ce dernier, il y a 4 fichiers importants pour nous:
<ul>
<li>app.module.ts
<li>app.component.html
<li>app.component.ts
<li>app.component.css
</ul>
<br>

### *app.module.ts* nous permettra d'importer nos composants et/ou des modules venant d'autres libraries.
<br>

### *app.component.html*, *app.component.ts*, *app.component.css* forment à eux trois le composant de la page où nous sommes arrivés après avoir fait *ng serve*.
<br>

### Ce qui se trouve dans ce composant sera affiché sur toutes les pages que vous créerez par la suite, idéal pour afficher une barre de navigation par exemple.
<br>

### Vous pouvez aller dans *app.component.html* et supprimer tout ce qu'il y a entre les deux blocs de commentaires afin de pouvoir y mettre votre code.
<br>

---
<br>

## Mon premier composant
<br>

### Nous allons créer un composant **navBar**.

### Pour créez un nouveau composant, il suffit de taper :
<br>

```

ng generate component {{YourComponentName}}

```

### ou en abrévié:
<br>

```

ng g c {{YourComponentName}}

```
<br>

### Un dossier *nav-bar* devrait être apparu dans le dossier *app* et le composant **NavBar** devrait avoir été ajouté automatiquement dans le fichier *app.module.ts*.
<br>

![app folder with navbar folder](/assets/app_folder_navbar.png)

<br>

### Comme nous voulons que notre barre de navigation soit sur toutes les pages, nous allons l'ajouter à *app.component.hmtl* avec la balise **\<app-nav-bar\>**
<br>

![app component htlm with navbar](/assets/app_html.png)
<br>

### Vous devriez voir *nav-bar works!* sur votre navigateur.
<br>

![nav bar works](/assets/nav-bar-works.png)
<br>

### Vous allez maintenant devoir créer une barre de navigation simple avec deux champs *Home* et *Products*.
<br>

![simple nav bar](/assets/simple-nav-bar.png)
<br>

### Une fois celle-ci terminée, nous allons ajouter la navigation.
<br>

---
<br>

## La navigation
<br>

### En Angular, pour naviguer on attribut à chaque route que l'on crée un composant qui sera la page de cette route.
<br>

### Nous allons donc devoir créer deux nouveaux composants, un composant *home* et un composant *products*.
<br>

![home & products components](/assets/home%26products.png)

<br>

### Il faudra ensuite créer un tableau de routes et importer le *RouterModule* avec ces dernières.
<br>

![routes](/assets/routes.png)

<br>

### Ajoutez les routes nécessaires dans le tableau grâce à la syntaxe suivante:
<br>

```

{ path: '{{YourPath}}',  component: {{YourComponent}} }

```
<br>

### Une fois cela terminer, il nous reste une dernière modification à faire.
<br>

### Dans votre *nav-bar.component.html*, ajoutez ceci à vos champs:
<br>

```

<p routerLink="{{YourPath}}">Home</p>

```
<br>

### Vos routes devraient maintenant fonctionner si vous cliquez sur un des champs.
<br>

![product route](/assets/products_route.png)

<br>

---
<br>

## Afficher une liste de produit

### Nous allons afficher une liste de produit. Pour cela nous allons tout d'abord créer une interface **Product**.

### Créez un fichier *product.ts* dans votre dossier *app*. Dans ce dernier ajoutez ceci.
<br>

![interface](/assets/interface.png)

<br>

### Ceci permet de déclarer une interface **Product** et de l'exporter pour pouvoir l'utiliser dans d'autre fichiers.

<br>

### Dans cette interface, il nous faut ajouter des attributs. Dans notre cas, vous devrez lui ajouter:
<br>

<ul>
  <li> name qui sera une string qui representera le nom du produit </li>
  <li> stock qui sera un nombre qui permettra de savoir la quantité restante de ce produit </li>
  <li> price qui sera un nombre qui representera le prix du produit  </li>
</ul>

<br>

### Une fois votre interface terminé, rendez vous dans *products.component.ts*, importez votre interface **Product** et créez un tableau de **Product**.
<br>

![product array](/assets/products_array.png)

<br>

### Dans ce tableau vous allez ajouter plusieurs produit:
<br>

<ul>
  <li>Des chaises qui coûteront 10$ et avec un nombre d'exemplaire de 4 </li>
  <li>Une table qui coûtera 100$ et avec un nombre d'exemplaire de 1 </li>
  <li>Un yacht qui coûtera 1$ et avec un nombre d'exemplaire de 0 </li>
</ul>

<br>

### Vous pouvez ajoutez d'autres produits si vous le voulez.

### Nous allons maintenant créer un composant pour afficher ces produits On l'appellera *productDisplayer*.

### Dans le *productDisplayer*, il nous faut récupérer la liste de produits qui est dans *products.component.ts* afin de l'afficher.

### Pour cela, il faut utliser *Input*:
<br>

![input](/assets/input.png)

<br>

### *Input* permetra de passer des variables dans la balise du composant, en mettant entre crochets le nom de la variable input = la variable que vous voulez passer dans le composant. C'est ce que nous allons faire dans *products.component.html*.
<br>

![product_html](/assets/products_html.png)
<br>

### On appelle cela le **Property Binding**.

### Maintenant que nous avons notre liste de produits, nous allons pouvoir l'afficher.

### Commençons par afficher un seul produit. Pour utiliser une variable qui est dans le *.ts* en html il suffit d'utiliser la syntaxe suivante:
<br>

```

{{YourVariableName}}

```
<br>

### Donc pour afficher un seul produit, cela ressemblerait à ça:
<br>

![product displayer html](/assets/product_displayer_html.png)
<br>

### Et donnerait cela sur le navigateur:
<br>

![product displayer web](/assets/product_displayer_web.png)

<br>

### Maintenant nous allons itérer sur la liste pour afficher tous les produits. En Angular, on utlise la directive [ngFor](https://angular.io/api/common/NgFor)


### En utilisant la directive, vous devriez pouvoir afficher toute la liste avec une seule ligne d'html:
<br>

![product displayer web full](/assets/products_displayer_web_full.png)
<br>

### C'est bien mais il est inutile d'afficher un produit si son stock est à 0, heureusement pour nous on peut afficher des éléments que si une condition est remplie, avec la directive [ngIf](https://angular.io/api/common/NgIf)
<br>

![product displayer web condition](/assets/product_displayer_web_condition.png)

<br>

### Je vous invite maintenant à rendre tout cela plus beau avec un peu de css.
<br>

### Nous allons maintenant imaginer que si l'utilisateur clique sur un produit c'est qu'il l'a acheté. Il faudra donc réduire le stock du produit à chaque clic.

### Pour cela, il suffit d'ajouter sur la balise du composant le nom de l'événement que l'on veut récupérer entre parenthèse = la fonction que vous voulez executer, dans notre cas le clic et une fonction pour décrementer le stock de notre produit:
<br>

![function](/assets/function.png)
<br>

### On appelle cela l'**Event Binding**

<br>

### Votre fonction *decrementStock* devra prendre en paramètre un **Product** et réduire son stock de 1.

### Une fois cela terminé, le stock du produit devrait se réduire à chaque clic:
<br>

![before clic](/assets/before_clic.png)
<br>

![after clic](/assets/after_clic.png)
<br>

### Il existe d'autres types de [*binding*](https://angular.io/guide/binding-syntax#binding-types-and-targets) que je vous invite à regarder, car ils pourraient vous être utiles dans certaines situtations.
<br>

---
<br>

## ViewChild & ViewChildren
<br>

### [ViewChild](https://angular.io/api/core/ViewChild) et [ViewChildren](https://angular.io/api/core/ViewChildren) sont des décorateurs permettant respectivement de récupérer une ou plusieurs [views](https://angular.io/guide/glossary#view), grâce au nom d'un composants, d'une directive ou d'une *template reference variable*, que nous verrons plus tard, et encore bien d'autre.
<br>

### Imaginons qu'en plus d'afficher notre liste de produit nous devions aussi afficher un produit seul. Nous allons donc créer un composant *product*. Il faudra donc modifer le **ProductComponentDisplayer** et le **ProductComponent** pour avoir le même affichage qu'auparavant.

<br>

### Maintenant il est tout a fait possible que nous ayons besoin de modifier un des produits depuis le **ProductDisplayerComponant**, c'est là qu'intervient  [ViewChild](https://angular.io/api/core/ViewChild) et [ViewChildren](https://angular.io/api/core/ViewChildren).

<br>

### Par exemple si l'on voulait récupérer la view d'un de nos **ProductComponent**, on le ferait ainsi:
<br>

![viewChildren](/assets/viewChildren.png)
<br>


### Grâce à cela nous avons une liste de tous les **ProductComponent** et pouvons accèder à leur attributs.

<br>

---
<br>

## Cycle de vie des composants

<br>

### Les composants angular possèdent ce qu'on appelle un cycle de vie, qui commence quand le composant est instancié et se termine quand il est détruit. Lors de ce cycle de vie, le composant appelle plusieurs méthodes appellées [*lifecycle hook methods*](https://angular.io/guide/lifecycle-hooks#lifecycle-event-sequence) qui permettent d'effectuer des actions tous au long du cycle de vie du composant.

### Ces méthodes peuvent être très utiles pour faire des actions spécifiques à moment précis.
<br>

### Par exemple, la méthode *ngOnInit* est une méthode propre à Angular et permet d'executer du code à la création d'un composant.
### Vous me direz peut-être qu'il existe déjà un constructeur pour cela mais il y a une différence. La méthode *ngOnInit* s'execute après le constructeur quand le composant a fini d'être construit.
<br>

### Imaginez que votre composant ait besoin besoin de faire une requête HTTP à votre serveur pour afficher certaines informations. Les composants doivent être simple et sans danger à construire, vous ne pouvez donc pas faire une requête dans le constructeur car elle pourrait échouer. C'est là qu'intervient *ngOnInit* qui s'execute peu après le constructeur et qui peut contenir du code plus important et "dangereux".
<br>

### Voici comment on utiliserait *ngOnInit* dans *products.component.ts*:
<br>

![ngOnInit](/assets/ngOnInit.png)
<br>

### Maintenant que vous connaissez le cycle de vie des composants et ViewChild et ViewChildren vous devriez être capable de modifier **ProductDisplayerComponent** afin que s'il ne reste qu'un seul exemplaire d'un produit il soit affiché en rouge (sans erreur console bien sûr).

<br>

![redproduct](/assets/redproduct.png)
<br>

### N'oubliez pas aussi de faire en sorte que, quand on clique pour réduire le stock jusqu'à 1, la couleur change bien.

<br>

### Il existe pleins d'autres [*lifecycle hook methods*](https://angular.io/guide/lifecycle-hooks#lifecycle-event-sequence) que je vous invite à voir car elles peuvent vraiment être très utiles. Mais attention, comme écrit dans la documentation Angular, certaines de ces méthodes sont appellées très souvent donc faites attention à ce que le code ne suit pas trop gourmant car cela pourrait impacter l'experience utilisateur.

<br>

---
<br>

## Les *template reference variables*
<br>

### Les [*template reference variables*](https://angular.io/guide/template-reference-variables) permettent d'utiliser les données d'un *template* (une balise par exemple) dans un autre *template* et sont donc vos meilleurs amis pour faire des formulaires avec [ngForm](https://angular.io/api/forms/NgForm) et [ngModel](https://angular.io/api/forms/NgModel).
<br>

### Elles permettent aussi de récupérer un ou plusieurs éléments avec *ViewChild* et *ViewChildren* vus précédemment.
<br>

### Pour les utiliser il suffit d'ajouter cette directive sur une de vos balises HTML:
<br>

```

#{{YourVariableName}}

```

### Je ne couvrirai pas en détail comment créer un formulaire car il existe plusieurs manières différentes d'en créer et tout dépend de ce dont vous avez besoin.
<br>

### Cependant je vous invite à regarder les [guides](https://angular.io/guide/forms-overview) de la documentation Angular à ce sujet et/ou la documentation de l'API d'[*angular/forms*](https://angular.io/api/forms).

<br>

---
<br>

## Content Projecting
<br>

### Le [*content projecting*](https://angular.io/guide/content-projection) permet d'insérer de nouveaux élément à l'intérieur d'un composant depuis un autre composant.
<br>

### Ceci peut s'avérer très utiles afin de créer des composants très flexibles comme des pop-ups ou des cartes.
<br>

### Créez un composant *card* et faites le "squelette" de cette dernière et ajoutez du css pour rendre tout ça magnifique.

### Une fois le squelette terminé, il suffit d'ajouter la balise *ng-content* à l'endroit où vous voulez ajouter les éléments à l'intérieur de votre composant.
<br>

![ngcontent](/assets/ngcontent.png)


### Ajoutez trois cartes vides dans votre **HomeComponent**.
<br>

### Ensuite, ajoutez votre contenu entre le balise du sélecteur de votre composant et vous pourrez faire de "jolies" cartes facilement customisables.
<br>

![projection](/assets/projection.png)

<br>

![cards](/assets/cards.png)

<br>

---
<br>

## Les *directives*
<br>

### Il existe plusieurs types de directives :

- ### Les [attribute directives](https://angular.io/guide/attribute-directives) qui changent l'apparence et le comportement des composants Angular et des éléments du [DOM](https://developer.mozilla.org/fr/docs/Glossary/DOM)
- ### Les [structural directives](https://angular.io/guide/structural-directives) qui change la dispostion du [DOM](https://developer.mozilla.org/fr/docs/Glossary/DOM) en ajoutant ou enlevant des éléments à ce dernier.

### Les [built-in directives](https://angular.io/guide/built-in-directives) sont des directives (*attribute* ou *structural*) déjà existante dans Angular telles que **ngIf* et **ngFor* qui sont très utiles. Je vous invite donc à vous renseigner dessus ces dernières.

### Vous pouvez créez vos propres directives avec la commande suivante:
<br>

```

ng generate directive {{YourDirectiveName}}

```

### ou en abrévié:
<br>

```

ng g d {{YourDirectiveName}}

```
<br>

### Pour utiliser une directive il suffit d'ajouter le nom de la directive sur la balise HTML de votre choix.
<br>

### Comme les formulaires, l'implémentation des directives dépendent de ce que vous voulez faire, donc je ne couvrirai pas ce point.
<br>

### Il existe par contre de très bon exemple pour implémenter une directive simple sur la documentation Angular pour les deux types de directives.

### Je vous invite donc à cliquer :

- ### [ici](https://angular.io/guide/attribute-directives#building-an-attribute-directive) pour l'exemple sur les *attribute directives*
- ### [ici](https://angular.io/guide/structural-directives#creating-a-structural-directive) pour l'exemple sur les *structural directives*

<br>

---
<br>

## Les *services*
<br>

### Cette section n'est pas terminée mais n'hésitez pas regarder les [services](https://angular.io/tutorial/tour-of-heroes/toh-pt4) sur la documentation Angular.
<br>

---
<br>

## Les *feature modules*
<br>

### Cette section n'est pas terminée mais n'hésitez pas regarder les [feature modules](https://angular.io/guide/feature-modules) sur la documentation Angular.
<br>

---
<br>

## Merci
<br>

### Les trois dernières sections ne sont pas terminées mais sont très importantes si vous comptez créer un vraie application afin d'avoir une bonne organisation de votre code et de votre projet.
<br>

### C'est la fin de ce workshop, j'espère que vous aurez apprécié et que cela vous sera utile.
