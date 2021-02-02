# Zoom sur les arbres de la Capitale
Pour l'examen d'Antoine Courtin 
<br/><br/>

**Sommaire:**

 
* [Jeux de données](#som1)
  * [Les arbres, Paris Data](#som1a)
  * [Les arbres remarquables, Paris Data](#som1b)
* [Les arbres de Paris](#som2)
  * [Les espèces d'arbres à Paris](#som2a)
  * [Répartition géographique des Arbres de Paris](#som2b)
* [Les arbres remarquables de Paris](#som3)
  * [Qu'est ce qu'un arbre remarquable ? ](#som3a)
  * [Répartition des arbres remarquables de Paris selon le lieu et l'espèce](#som3b)
  * [Année de plantation des arbres remarquables de Paris](#som3c)
* [Explications](#som4)



## 1. Jeux de données <a id="som1"></a>

## A. Jeu de données n°1 : Les arbres, Paris Data <a id="som1a"></a>

<iframe src="https://data.opendatasoft.com/explore/embed/dataset/les-arbres@parisdata/table/?disjunctive.typeemplacement&disjunctive.arrondissement&disjunctive.libellefrancais&disjunctive.genre&disjunctive.espece&disjunctive.varieteoucultivar&disjunctive.stadedeveloppement&disjunctive.remarquable&static=false&datasetcard=false" width="800" height="300" frameborder="0"></iframe>
<br/>

Ce premier jeu de données relativement volumineux selectionné sur Opendatasoft contient 204 796 enregistrements. Il a été crée par la Direction des Espaces Verts et de l'Environnement de la Mairie de Paris.  
Il s'agit d'un recensement de l’ensemble des arbres présents sur le territoire parisien et des cimetières extra-muros.  
Dans ce jeu de données sont renseignées les coordonnées géographiques, la mensuration, la classification et l'année de plantation des arbres.
<br/><br/>

## B. Jeu de données n°2 : Les arbres remarquables, Paris Data <a id="som1b"></a>

<iframe src="https://data.opendatasoft.com/explore/embed/dataset/arbresremarquablesparis@parisdata/table/?&static=false&datasetcard=false" width="800" height="300" frameborder="0"></iframe> 
<br/>
Le second jeu de données également selectionné sur Opendatasoft contient seulement 179 enregistrements et a été crée par la Direction des Espaces Verts et de l'Environnement de la Mairie de Paris. 
Il s'agit dans une certaine mesure d'un "extrait" du premier jeu de données dans la mesure où nous retrouvons ici tous les arbres du premier recensement pour lesquels la valeur du champ 'REMARQUABLE' était 'OUI'. Soit 179 arbres sur 204 796.  
Dans ce jeu de données sont donc aussi renseignées les coordonnées géographiques, la mensuration, la classification et l'année de plantation des arbres remarquables de Paris.
<br/><br/>

## 2. Les arbres de Paris <a id="som2"></a>

### A. Les espèces d'arbres à Paris <a id="som2a"></a>

<iframe src="https://data.opendatasoft.com/chart/embed/les_genres_darbres_a_paris/?&static=false&datasetcard=false" width="800" height="600" frameborder="0"></iframe>

Type de graphique: Camembert

Source visualisation : Opendatasoft  
<br/><br/>


Cette première datavisualisation nous permet de mettre en évidence les principales espèces d'arbres que l'on retrouve au sein de la capitale. 
<br/><br/>

**Requête :**

````sparql
SELECT ?lemma ?item ?img
WHERE {
  VALUES ?lemma {
    "Platanus"@en
    "Aesculus"@en
    "Tilia"@en
  }
  ?sitelink schema:about ?item;
    schema:isPartOf <https://en.wikipedia.org/>;
    schema:name ?lemma.
    ?item wdt:P18 ?img.
}
````
<br/>

**Résultat :**

<iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23%C3%89l%C3%A9ments%20Wikidata%20d%E2%80%99articles%20Wikip%C3%A9dia%0A%23Returns%20a%20list%20of%20Wikidata%20items%20for%20a%20given%20list%20of%20Wikipedia%20article%20names%0A%23List%20of%20Wikipedia%20article%20names%20(lemma)%20is%20like%20%22WIKIPEDIA%20ARTICLE%20NAME%22%40LANGUAGE%20CODE%20with%20de%20for%20German%2C%20en%20for%20English%2C%20etc.%0A%23Language%20version%20and%20project%20is%20defined%20in%20schema%3AisPartOF%20with%20de.wikipedia.org%20for%20German%20Wikipedia%2C%20es.wikivoyage%20for%20Spanish%20Wikivoyage%2C%20etc.%0A%0ASELECT%20%3Flemma%20%3Fitem%20%3Fimg%0AWHERE%20%7B%0A%20%20VALUES%20%3Flemma%20%7B%0A%20%20%20%20%22Platanus%22%40en%0A%20%20%20%20%22Aesculus%22%40en%0A%20%20%20%20%22Tilia%22%40en%0A%20%20%7D%0A%20%20%20%0A%20%20%3Fsitelink%20schema%3Aabout%20%3Fitem%3B%0A%20%20%20%20schema%3AisPartOf%20%3Chttps%3A%2F%2Fen.wikipedia.org%2F%3E%3B%0A%20%20%20%20schema%3Aname%20%3Flemma.%0A%20%20%20%20%3Fitem%20wdt%3AP18%20%3Fimg.%0A%0A%7D" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups"></iframe>
<br/><br/>

### B. Répartition géographique des Arbres de Paris <a id="som2b"></a>

<iframe src="https://data.opendatasoft.com/chart/embed/?dataChart=eyJxdWVyaWVzIjpbeyJjb25maWciOnsiZGF0YXNldCI6Imxlcy1hcmJyZXNAcGFyaXNkYXRhIiwib3B0aW9ucyI6eyJkaXNqdW5jdGl2ZS50eXBlZW1wbGFjZW1lbnQiOnRydWUsImRpc2p1bmN0aXZlLmFycm9uZGlzc2VtZW50Ijp0cnVlLCJkaXNqdW5jdGl2ZS5saWJlbGxlZnJhbmNhaXMiOnRydWUsImRpc2p1bmN0aXZlLmdlbnJlIjp0cnVlLCJkaXNqdW5jdGl2ZS5lc3BlY2UiOnRydWUsImRpc2p1bmN0aXZlLnZhcmlldGVvdWN1bHRpdmFyIjp0cnVlLCJkaXNqdW5jdGl2ZS5zdGFkZWRldmVsb3BwZW1lbnQiOnRydWUsImRpc2p1bmN0aXZlLnJlbWFycXVhYmxlIjp0cnVlLCJ0aW1lem9uZSI6IkV1cm9wZS9CZXJsaW4ifX0sImNoYXJ0cyI6W3siYWxpZ25Nb250aCI6dHJ1ZSwidHlwZSI6ImNvbHVtbiIsImZ1bmMiOiJDT1VOVCIsInlBeGlzIjoiaWRiYXNlIiwic2NpZW50aWZpY0Rpc3BsYXkiOnRydWUsImNvbG9yIjoiIzE5NjMwQSIsInBvc2l0aW9uIjoiY2VudGVyIiwieVJhbmdlTWluIjoiIiwieVJhbmdlTWF4IjoiIiwiZGlzcGxheVZhbHVlcyI6dHJ1ZSwiZGlzcGxheVN0YWNrVmFsdWVzIjpmYWxzZX1dLCJ4QXhpcyI6ImFycm9uZGlzc2VtZW50IiwibWF4cG9pbnRzIjpudWxsLCJzb3J0Ijoic2VyaWUxLTEiLCJzZXJpZXNCcmVha2Rvd24iOiIiLCJzZXJpZXNCcmVha2Rvd25UaW1lc2NhbGUiOiIifV0sInRpbWVzY2FsZSI6IiIsImRpc3BsYXlMZWdlbmQiOnRydWUsImFsaWduTW9udGgiOnRydWUsImxhYmVsc1hMZW5ndGgiOjE3fQ%3D%3D&static=false&datasetcard=false" width="800" height="600" frameborder="0"></iframe>

Type de graphique: Colonne

Source visualisation : Opendatasoft
<br/><br/>


## 3. Les arbres remarquables de Paris <a id="som3"></a>

### A.  Qu'est ce qu'un arbre remarquable ? <a id="som3a"></a>
<br/>
Tout d'abord il faut savoir qu'un arbre est dit remarquable lorsqu'on le remarque ! Il peut se distinguer par ses mensurations, son aspect, son identité ou encore son âge.

Cette requête Wikidata nous permet de visualiser plusieurs arbres remarquables du territoire français.
<br/>

**Requête :**

````sparql
select distinct ?item ?itemLabel ?img
where {
  ?item wdt:P31 wd:Q811534 .
  ?item wdt:P17 wd:Q142 .
  ?item wdt:P18 ?img . 
    SERVICE wikibase:label {
        bd:serviceParam wikibase:language "fr" .
    }}
````
<br/>

**Résultat :**

<iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#select%20distinct%20%3Fitem%20%3FitemLabel%20%3Fimg%0Awhere%20%7B%0A%20%0A%20%20%3Fitem%20wdt%3AP31%20wd%3AQ811534%20.%0A%20%20%3Fitem%20wdt%3AP17%20wd%3AQ142%20.%0A%20%20%3Fitem%20wdt%3AP18%20%3Fimg%20.%20%0A%20%20%20%20SERVICE%20wikibase%3Alabel%20%7B%0A%20%20%20%20%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22fr%2Cen%22%20.%0A%20%20%20%20%7D%7D" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups"></iframe>


<br/><br/>
### B.  Répartition des arbres remarquables de Paris selon le lieu et l'espèce  <a id="som3b"></a>

<div class="flourish-embed flourish-hierarchy" data-src="visualisation/5126605"><script src="https://public.flourish.studio/resources/embed.js"></script></div>


On apprend dans la rubrique "Arbres" du site officiel de la ville de Paris que si les platanes, les hêtres et les marronniers sont les plus représentés parmi les arbres remarquables, c'est à cause de leur longévité et de leur port impressionnant.

Type de graphique: Treemap

Source visualisation : Flourish
<br/><br/>

### C. Année de plantation des arbres remarquables de Paris  <a id="som3c"></a>

<iframe src="https://data.opendatasoft.com/chart/embed/?dataChart=eyJxdWVyaWVzIjpbeyJjaGFydHMiOlt7InR5cGUiOiJsaW5lIiwiZnVuYyI6IkNPVU5UIiwieUF4aXMiOiJpZGJhc2UiLCJzY2llbnRpZmljRGlzcGxheSI6dHJ1ZSwiY29sb3IiOiIjMTk2MzBBIiwicG9zaXRpb24iOiJjZW50ZXIifV0sInhBeGlzIjoiZGF0ZXBsYW50YXRpb24iLCJtYXhwb2ludHMiOiIiLCJ0aW1lc2NhbGUiOiJ5ZWFyIiwic29ydCI6IiIsImNvbmZpZyI6eyJkYXRhc2V0IjoiYXJicmVzcmVtYXJxdWFibGVzcGFyaXNAcGFyaXNkYXRhIiwib3B0aW9ucyI6eyJ0aW1lem9uZSI6IkV1cm9wZS9CZXJsaW4ifX0sInNlcmllc0JyZWFrZG93biI6IiIsInNlcmllc0JyZWFrZG93blRpbWVzY2FsZSI6IiJ9XSwiZGlzcGxheUxlZ2VuZCI6dHJ1ZSwiYWxpZ25Nb250aCI6dHJ1ZSwidGltZXNjYWxlIjoieWVhciJ9&static=false&datasetcard=false" width="800" height="600" frameborder="0"></iframe>


Type de graphique: Ligne

Source visualisation : Opendatasoft

<br/>

## 4. Explications <a id="som4"></a>

Tout d'abord il peut sembler étonnant qu'aucune datavisualisation de type carte géographique n'ait été présentée ici malgré la présence des coordonnées géographiques dans les deux jeux de données. C'est tout simplement car ce format m'a semblé n'apporter aucune plus-value pour les deux jeux de données, contrairement au graphique sous forme de colonne qui permet de mettre en évidence en un coup d'oeil la répartition des arbres sur le sol parisien. 

Ensuite, il m'est nécessaire de préciser qu'il m'a été impossible de travailler avec le premier jeu de données (Les Arbres, ParisData) ailleurs que sur OpenDataSoft. À cause de sa taille volumineuse (ou peut-être de ma mauvaise connexion internet) je n'ai pu utiliser ni Rawgraphs, Flourish ou Datawrapper sans les faire "crasher" au moment d'entrer le jeu de données, que ce soit en le joignant en .csv ou simplement en effectuant un copié/collé.

C'est pourquoi j'ai finalement réalisé les datavisulations du premier jeu de données directement sur OpenDataSoft. 


Concernant le travail sur OpenRefine, il m'a été possible de copier/coller les données, de les modifier, mais pas de les exporter car une page d'erreur s'affichait, ce qui n'arrive jamais avec un fichier plus léger. C'est dommage car quelques erreurs avaient pu être repérées, notamment grâce à la fonctionnalité grouper et éditer : 
<br/><br/>
![](https://zupimages.net/up/21/05/4fpz.jpg)
<br/><br/>
Toutefois les deux espèces d'arbres concernées sont tellement minoritaires par rapport aux autres catégories que les datavisualisations ne semblent pas être faussées.


