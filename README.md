# pjl-retraites
***Version appliquée du projet de loi instituant un système de retraite universel***

## But du projet

Les projets de loi étant écris sous la forme d'instructions modifiant différents codes, il pourrait être plus simple de travailler avec ces modifications sous la forme de différences sur le contenu directement. L'Assemblée publie par exemple des [textes comparatifs](http://www.assemblee-nationale.fr/15/ta-pdf/0911-p.pdf#page=3) pour aider les parlementaires.

Le projet est donc d'appliquer les "instructions" de chaque article du projet de loi pour ensuite produire un texte comparatif.

![exemple avec l'article 1er](diff_article1.png?raw=true)

## Organisation

- La branche `loi-en-vigeur` contient les codes et lois avant modification
- Les branches `articles-<numéro de l'article>` se basent sur la `loi-en-vigeur` et appliquent l'article.
    * Ces branches un seul commit. Dans le message de commit, on peut mettre que celle-ci est en cours de fabrication avec un titre comme `Article [<<où l'on en est>>]`, ex `Article 14 [1]` veut dire que le `I.` de l'Article 14 à été fait mais pas le reste par exemple.
    * Pour les article qui ne modifient pas de codes et sont directement applicables, un nouveau fichier est crée, `loi`
- Une branche `pjl-prep` est ensuite crée à la main en faisant un *merge* de tout les articles. Les conflits sont résolus à la main pour le moment.

À la base, le projet étant simplement de retranscrire le projet préparatoire mais j'ai commencé à ajouter [la version déposée à l'AN](http://www.assemblee-nationale.fr/15/projets/pl2623.asp) sous la forme de branches `article-XXX-depot`, par exemple: https://github.com/regardscitoyens/pjl-retraites/compare/article-001...article-001-depot

De même, les amendements sont ajoutés sous la forme de branches `article-XXX-amendement-YYY`.

De plus, le même procédé est appliqué à [la loi organique](http://www.assemblee-nationale.fr/15/projets/pl2622.asp), en ajoutant simplement le prefixe `pjlo/` devant. Les articles sont par exemple disponibles sous `pjlo/article-XXX-depot`.

## Comment participer ?

### Ajouter un article

Tout les 64 articles du projet du loi ne sont pas encore fait, la façon la plus simple de participer est d'en faire un qui n'est pas encore fait.

 1. Télécharger le projet de loi, il est disponible chez [Contexte](https://www.contexte.com/article/pouvoirs/document-les-projets-de-loi-de-reforme-des-retraites_109875.html) en créant un compte gratuit, de même chez [Politis](https://www.politis.fr/articles/2020/01/documents-les-textes-de-la-reforme-des-retraites-a-telecharger-41246/)
 2. Prendre un article, ceux-ci commencent à partir de la **page 45**
     * **Les articles déja fait sont documentés [ici](https://github.com/regardscitoyens/pjl-retraites/issues/5)**
3. Modifier la loi en vigeur
    * Si l'article modifie un code, il faut éditer ce code
    * Si l'article s'applique directement, alors il faut créer un nouveau fichier `loi`, et mettre dans ce fichier l'article et son texte, comme à [l'article 18](https://github.com/regardscitoyens/pjl-retraites/compare/loi-en-vigeur...article-018).

**Si besoin d'aide, n'hesitez pas me contacter via un courriel à `damien@dam.io`**

De plus, si vous voyez une erreur dans le projet de loi, vous pouvez la signaler ici: https://github.com/regardscitoyens/pjl-retraites/issues/1

### Idées d'améliorations

- Formater le résultat pour qu'il soit utilisable par des non-spécialistes 
	- Par exemple: les textes comparatifs de l'Assemblée, les diff Markdown riches comme ceux de GitHub et Wikipedia
- Faire le même procédé pour la version organique

### Inspirations

- [Duralex/Sedlex](https://github.com/Legilibre/SedLex) qui automatise ce qui est fait ici à la main
- [La Fabrique de la loi](http://lafabriquedelaloi.fr/) qui produit un equivalent des textes comparatifs en permettant de comparer les version des projets de loi
