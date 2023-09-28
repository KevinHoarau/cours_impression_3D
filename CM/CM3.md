---
marp: true
paginate: true
class: slide
theme: khoarau
---

<!-- _class: title -->
![bg left:40% 80%](images/cm3/grande_roue.png)
# ***CAO pour l'impression 3D***
## Modélisation 3D
Kévin Hoarau - Septembre 2023

---
<!-- header: CAO pour l'impression 3D -->
<!-- _class: title -->
# ***Conception assistée par ordinateur (CAO)***

---

# Conception assistée par ordinateur (CAO)


<div class="columns" style="--split: 2fr 1fr ">
<div>

* Les logiciels de conception assistée par ordinateur (CAO) ou *computer aided design* (CAD) permettent d'effectuer des modélisations géométriques afin de concevoir des produits.
* Certains logiciels de CAO permettent également de tester le produit virtuellement à l'aide de simulations numériques.
* Le terme de modélisation 3D est souvent utilisé pour désigner la pratique de la CAO 3D.


</div>
<div>  

<br>

![center](images/cm3/fusion360_simulation.webp)
<div class="image_caption">Exemple de simulation dans Fusion 360</div>

</div>
</div>

---

# Catégories de logiciels de CAO 3D

<div class="columns" style="--split: 1.5fr 1fr ">
<div>

* **Facilité de prise en main :** Tinkercad, Sketchup, ...

* **Conception paramétrique :** Solidworks, Fusion 360, FreeCAD, Onshape, ...

* **Langage de programmation :** OpenSCAD

* **Logiciel d'infographie 3D :** Blender, Maya, ZBrush, ...


</div>
<div>  

<br>

![center](images/cm3/cad_softwares.png)
<div class="image_caption">Exemples de logiciels de CAO 3D</div>
<div class="image_caption">("Selecting a free 3D CAD option", Teaching Tech)</div>

</div>
</div>

---

# Dans ce cours

* Nous utiliserons des logiciels de conception paramétrique.
* Je recommande l'utilisation d'Onshape pour son fonctionnement dans le cloud (malgrès une politique tarifaire discutable).
* Fusion 360 est également une bonne alternative, mais nécessite une installation.
* Pour les amoureux de l'open-source et les plus aventureux, FreeCAD sera votre compagnon idéal. 


---

<!-- _class: title -->
# ***Introduction à la conception paramétrique***

---

# Esquisse

<div class="columns" style="--split: 2fr 1fr ">
<div>


* Le point de départ de toutes modélisations 3D est généralement la création d'une d'esquisse ou *sketch*
* Elle permet de dessiner des formes en 2D qui seront ensuite utilisées pour construire des solides en 3D.
* En combinant des formes et des contraintes géométriques il est possible de construire des formes complexes.

</div>
<div>  

<br>

![center](images/cm3/sketch_example.png)
<div class="image_caption">Exemple de construction d'un solide à partir d'une esquisse</div>
</div>
</div>

---

# Création d'une esquisse

<div class="columns" style="--split: 1.5fr 1fr ">
<div>

* Une esquisse doit être créée à partir d'un plan.
* Si le projet ne contient aucun solide alors on prendra un plan parmi $(x,y)$, $(x,z)$ ou $(y,z)$.
* Il est également possible d'utiliser une face d'un solide comme plan pour la construction de l'esquisse.


</div>
<div>  

<br>

![center](images/cm3/esquisse_face.png)
<div class="image_caption">Exemple de construction d'une esquisse à partir d'une face</div>
</div>
</div>


---

# Les outils de base de l'esquisse

<div class="columns" style="--split: 2fr 1fr ">
<div>

* **Formes :** de nombreuses formes sont disponibles : lignes, rectangles, cercles, arcs, polygones, *etc*.
* **Mode construction :** le mode construction permet de dessiner une forme qui sera utilisée pour construire d'autres formes sans quelle soit prise en compte lors de la création du solide.
* **Contraintes :** des contraintes géométriques peuvent être définies sur les formes : côte, égal, parallèle, tangente, *etc*.

</div>
<div>  

<br>

![center](images/cm3/sketch_contraintes.png)
<div class="image_caption">Deux cercle et une ligne de construction (contraintes appliquées : côtes, égal et tangente)</div>

</div>
</div>

---

# Les outils de répétitions

Les outils de répétitions permettent de créer une ou plusieurs formes à partir d'une forme existante.

Le **décalage** permet de reproduire une forme de manière concentrique :

![center h:300](images/cm3/decalage.png)

---

# Les outils de répétitions

Les outils de répétitions permettent de créer une ou plusieurs formes à partir d'une forme existante.

Le **miroir** permet d'appliquer une symétrie axiale :

![center h:250](images/cm3/miroir.png)

---

# Les outils de répétitions

Les outils de répétitions permettent de créer une ou plusieurs formes à partir d'une forme existante.

La **répétition linéaire** permet de reproduire une forme sur une grille :

![center h:300](images/cm3/repetition_lineaire.png)

---

# Les outils de répétitions

Les outils de répétitions permettent de créer une ou plusieurs formes à partir d'une forme existante.

La **répétition circulaire** permet de reproduire une forme sur un cercle :

![center h:300](images/cm3/repetition_circulaire.png)

---

# Les variables


<div class="columns" style="--split: 1.2fr 1fr ">
<div>

* L'utilisation de variables est une bonne pratique permettant de modifier rapidement une modélisation.
* Lorsque la variable est modifié les changements sont appliqués en cascades aux esquisses et aux solides construits à partir des esquisses.

</div>
<div>  

![center w:1000](images/cm3/variable_1.png)
<div class="image_caption">Déclaration d'une variable</div>

<br>

![center h:200](images/cm3/variables_2.png)
<div class="image_caption">Utilisation d'une variable</div>

</div>
</div>


---

# Création d'un solide

<div class="columns" style="--split: 2fr 1fr ">
<div>

## Extrusion

* L'opération la plus courante pour créer un solide à partir d'une esquisse est l'extrusion.

* Si le nouveau solide entre en contact avec un solide existant alors il est possible d'effectuer des opérations booléennes : union, intersection, différence (*e.g.* perçage).


</div>
<div>  

![center w:400](images/cm3/extrude_remove.png)
<div class="image_caption">Exemple de percage à l'aide d'une extrusion</div>

</div>
</div>

---

# Création d'un solide


<div class="columns" style="--split: 2fr 1fr ">
<div>

## Révolution

* Un autre opération très utile est la révolution.
* Elle permet d'extruder une esquisse en effectuant une rotation autours d'un axe.


</div>
<div>  

</br></br>

![center w:1000](images/cm3/revolution.png)
<div class="image_caption">Exemple revolution</div>

</div>
</div>

---

# Création d'un solide


<div class="columns" style="--split: 2fr 1fr ">
<div>

## Balayage

* Le balayage permet d'effectuer une extrusion en suivant une courbe. 
* La courbe utilisée peut prendre est libre et peut prendre n'importe qu'elle forme
* Cette opération est souvent utilisée pour créer des pas de vis.


</div>
<div>  

![center h:400](images/cm3/balayage.png)
<div class="image_caption">Exemple de balayage</div>

</div>
</div>

---

# Opérations sur les solides


<div class="columns" style="--split: 2fr 1fr ">
<div>

## Opérations booléennes

* Les opérations booléennes s'appliques sur deux solides qui sont en contact
* Les opérations possible sont : l'union, l'intersection et la différence.


</div>
<div>  

![center w:1000](images/cm3/intersection.png)
<div class="image_caption">Exemple d'intersection entre deux cylindres</div>

</div>
</div>

---

# Opérations sur les solides


<div class="columns" style="--split: 2.5fr 1fr ">
<div>

## Congés et chanfreins

* Les congés et chanfreins permettent de rendre les arêtes d'un solide moins abrupt.
* Un congé permet d'obtenir une arête arrondie.
* Un chanfrein permet d'obtenir une arête inclinée.


</div>
<div>  

![center w:1000](images/cm3/congé_chanfrein.png)
<div class="image_caption">Exemple de congé (à gauche) et de chanfrein (à droite) de 5mm</div>

</div>
</div>

---


# Opérations sur les solides


<div class="columns" style="--split: 2.5fr 1fr ">
<div>

## Opérations de répétitions

* Comme pour les esquisses, il existe des opérations de répétitions
* L'opération miroir applique une symétrie à l'aide d'un plan de symétrie
* Les opérations de répétitions linéaires et circulaires permettent de reproduire un solide sur une grille ou un cercle.


</div>
<div>  

</br>

![center w:1000](images/cm3/solide_repetition_lineaire.png)
<div class="image_caption">Exemple de répétition linéaire</div>

</div>
</div>

---


<!-- _class: title -->
# ***Bonnes pratiques de modélisation***
# ***pour l'impression 3D***

---

# Eviter les supports

* Dès la phase de conception, il faut penser à l'orientation que va avoir votre pièce durant d'impression.
* Il faut alors éviter de créer des angles trop importants.

</br>

<div class="columns" style="--split: 1fr 1fr ">
<div>

![center h:250](images/cm3/support_required.png)
<div class="image_caption">Pièce nécessitant des supports</div>

</div>
<div>  

![center h:250](images/cm3/support_not_required.png)
<div class="image_caption">Ajout d'un chanfrein</div>

</div>
</div>

---

# Penser aux tolérances

<div class="columns" style="--split: 2.5fr 1fr ">
<div>

* L'impression 3D est un processus de fabrication imparfait.
* Si deux pièces doivent s'imbriquer, il faut penser à laisser des tolérances suffissantes.
* Généralement un espace de 0.5mm est suffisant.
* On peut également laisser un espace plus grand, mais cela créera du jeu.

</div>
<div>  

</br>

![center w:1000](images/cm3/tolerances.png)
<div class="image_caption">Deux solides espacés de 0.5mm.</div>

</div>
</div>

---

# Autres considérations

* Prendre en compte volume d'impression de l'imprimante.
- Ne pas créer de parois ou des détails trop fins. L'imprimante à une buse de 0.4mm et une hauteur de couche minimum de 0.1mm.
- La pièce doit avoir une surface plane, sinon il faudra des supports.

<div class="columns" style="--split: 1fr 1fr ">
<div>

![center h:220](images/cm3/no_plan.png)
<div class="image_caption">Pièce sans surface plane</div>

</div>
<div>  

![center h:220](images/cm3/plan.png)
<div class="image_caption">Pièce avec une surface plane</div>

</div>
</div>


---

# Vérifier sa modélisation

<div class="columns" style="--split: 0.9fr 1fr ">
<div>

Deux outils pratiques :
* L'outil de mesure permet de vérifier les côtes.
* Le plan de coupe permet de visualiser une section de la pièce.

</div>
<div>  

<br>

![center w:1000](images/cm3/measure.png)
<div class="image_caption">Plan de coupe et outil de mesure</div>

</div>
</div>

---

<!-- _class: title -->
# ***Un peu de pratique***

---

# Exercice 1 : la boite

<div class="columns" style="--split: 1.5fr 1fr ">
<div>

Nous allons créer une boite paramétrique.

Les variables suivantes pourront être ajustées pour modifier la boite :
* hauteur, longueur et largeur
* épaisseur des murs
* tailles des congés.

</div>
<div>  

<br>

![center w:1000](images/cm3/exercice_boite.png)
<div class="image_caption">Résultat attendu</div>

</div>
</div>


---

# Exercice 2 : le couvercle

<div class="columns" style="--split: 1.5fr 1fr ">
<div>

Nous allons maintenant créer un couvercle.

Les variables suivantes pourront être ajustées :
* hauteur, longueur et largeur
* tolérance pour le montage du couvercle sur la boite
* tailles des congés,
* le diamètre des trous

</div>
<div>  

<br>

![center w:1000](images/cm3/couvercle.png)
<div class="image_caption">Résultat attendu</div>

</div>
</div>

---

# Exercice 3 : le verre



Utilisez l'outil de révolution pour créer un verre à pied.

<br>

![center h:300](images/cm3/verre.png)
<div class="image_caption">Exemple de résultat</div>

