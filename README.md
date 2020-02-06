# pjl-retraites
***Version Git du projet de loi instituant un système de retraite universel***

## But du projet

Les projets de loi étant écris sous la forme d'instructions modifiant différents codes, il pourrait être plus simple de travailler avec ces modifications sous la forme de différences sur le contenu directement. L'Assemblée publie par exemple des [textes comparatifs](http://www.assemblee-nationale.fr/15/ta-pdf/0911-p.pdf#page=3) pour aider les parlementaires.

<!-- TODO: insérer un screenshot de comparaison et un lien vers une branche sympa -->

Le projet est donc d'appliquer les "instructions" de chaque article pour ensuite produire un texte comparatif.

Exemple pour l'Article 4 du projet de loi cela donne ceci: https://github.com/regardscitoyens/pjl-retraites/compare/loi-en-vigeur...article-004


## Organisation

- La branche `loi-en-vigeur` contient les codes et lois avant modification
- Les branches `articles-<numéro de l'article>` se basent sur la `loi-en-vigeur` et appliquent l'article.
    * Ces branches doivent idéalement n'avoir qu'un seul commit. Dans le message de commit, on peut aussi mettre que celle-ci est en cours de fabrication avec un titre comme `Article [<<où l'on en est>>]`, ex `Article 14 [1]` veut dire que le `I.` de l'Article 14 à été fait mais pas le reste por exemple.
    * Pour les article qui ne modifient pas de codes et sont directement applicables, un nouveau fichier est crée, `loi`, ce fichier est destinés à acceuillir tout les articles 
- Une branche `PJL-retraites` est ensuite crée à la main en faisant un *cherry-pick* de tout les articles. Des conflits vont apparaitres, ils doivent être résolus à la main pour le moment.

## Comment participer ?

### Ajouter un article

Tout les 64 articles du projet du loi ne sont pas encore fait, la façon la plus simple de participer est d'en faire un qui n'est pas encore fait.

 1. Télécharger le projet de loi, il est disponible chez [Contexte](https://www.contexte.com/article/pouvoirs/document-les-projets-de-loi-de-reforme-des-retraites_109875.html) en créant un compte gratuit, de même chez [Politis](https://www.politis.fr/articles/2020/01/documents-les-textes-de-la-reforme-des-retraites-a-telecharger-41246/)
 2. Prendre un article, ceux-ci commencent à partir de la **page 45**
     * **Les articles 1 à 20 ont déja été commencés**, il vaut mieux prendre les articles à partir de **30**
     * Il est possible de vérifier l'état d'avancement d'un article en allant regarder dans sa branche respective
3. Modifier la loi en vigeur
    * Si l'article modifie le code de la sécurité sociale, il faut éditer ce code, celà n'est pas possible avec l'interface GitHub car ce code est trop long po. Il faut [télécharger le code](https://archeo-lex.fr/codes/code_de_la_s%C3%A9curit%C3%A9_sociale/2019-08-14/brut), le modifier avec un éditeur de texte, comme Notepad++ pour Windows. Et m'envoyer le résultat par email. Si vous connaissez bien Git et Github, alors faire une Pull Request avec le résultat 
    * Si l'article modifie un autre code, celà n'est pas encore supporté, il faudrait l'ajouter depuis Archeolex dans `loi-en-vigeur`.
    * Si l'article s'applique directement, alors il faut créer un nouveau fichier `loi`, celà peut [se faire via l'interface GitHub](https://github.com/regardscitoyens/pjl-retraites/new/loi-en-vigeur?filename=loi), et mettre dans ce fichier l'article et son texte, comme dans à [l'article 18](https://github.com/regardscitoyens/pjl-retraites/compare/loi-en-vigeur...article-018).

**Si besoin d'aide, n'hesitez pas me contacter via un courriel à `damien@dam.io`**

De plus, si vous voyez une erreur dans le projet de loi, vous pouvez la signaler ici: https://github.com/regardscitoyens/pjl-retraites/issues/1

À la base, le projet étant simplement de retranscrire le projet préparatoire mais j'ai commencé à ajouter [la version déposée à l'AN](http://www.assemblee-nationale.fr/15/projets/pl2623.asp) sous la forme de branches `article-XXX-depot`, par exemple: https://github.com/regardscitoyens/pjl-retraites/compare/article-001...article-001-depot

### Idées d'améliorations

- Formater le résultat pour qu'il soit utilisable par des non-spécialistes 
	- Par exemple: les textes comparatifs de l'Assemblée, les diff Markdown riches comme ceux de GitHub et Wikipedia
- Faire le même procédé pour la version organique
