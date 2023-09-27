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

* Les logiciels de conception assistée par ordinateur (CAO) ou *computer aided design* (CAD) permettent d'effectuer des modélisations géométriques afin concevoir des produits.
* Certains logiciels de CAO permettent également de tester le produits virtuellement à l'aide de simulations numériques.
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
* Je recommande l'utilisation d'Onshape pour son fonctionnement dans le cloud (malgrè une politique tarifaire discutable ...)
* Fusion 360 est également une bonne alternative, mais nécessite une installation.
* Pour les amoureux de l'open-source et les plus aventureux, FreeCAD sera votre conpagnon idéal. 


---

<!-- _class: title -->
# ***Introduction à la conception paramétrique***

---

# Esquisse

<div class="columns" style="--split: 2fr 1fr ">
<div>


* Le point de départ de toutes modélisations 3D est généralement la création d'une d'esquisse ou *sketch*
* Elle est créée à partir d'un plan.
* Elle permet de dessiner des formes en 2D qui seront ensuite utilisées pour construire une forme en 3D.
* En combinant des formes et des contraintes géométriques il est possible de construire des formes complexes.

</div>
<div>  

<br>

![center](images/cm3/sketch_example.png)
<div class="image_caption">Exemple de construction d'un forme 3D à partir d'une esquisse</div>
</div>
</div>

---

# Les outils de base de l'esquisse

<div class="columns" style="--split: 2fr 1fr ">
<div>

* Les formes : de nombreuses formes sont généralement disponibles : lignes, rectangles, cercles, arcs, polygones, *etc*
* Le mode construction : le dessin d'une forme en mode construction permet d'utiliser cette dernière pour construire d'autre forme sans quelle soit prise en compte lors de la création de la forme 3D
* Les contraintes : de nombreuse contraintes géométriques peuvent être définies sur les formes : côte, égal, parallèle, tangente, *etc*

</div>
<div>  

<br>

![center](images/cm3/sketch_contraintes.png)
<div class="image_caption">Deux cercle et une ligne de construction (contraintes appliquées : côtes, égal et tangente)</div>

</div>
</div>

---

# Les outils de répétitions

Les outils de répétitions permettent de créér une ou plusieurs formes à partir d'une forme existante.

Le **décalage** permet de reproduire une forme de manière concentrique :

![center h:300](images/cm3/decalage.png)

---

# Les outils de répétitions

Les outils de répétitions permettent de créér une ou plusieurs formes à partir d'une forme existante.

Le **miroir** permet d'appliquer de symétrie axiale :

![center h:300](images/cm3/miroir.png)

---

# Les outils de répétitions

Les outils de répétitions permettent de créér une ou plusieurs formes à partir d'une forme existante.

La **répétition linéaire** permet de reproduire une forme sur une grille :

![center h:300](images/cm3/repetition_lineaire.png)

---

# Les outils de répétitions

Les outils de répétitions permettent de créér une ou plusieurs formes à partir d'une forme existante.

La **répétition circulaire** permet de reproduire une forme sur un cercle :

![center h:300](images/cm3/repetition_circulaire.png)

---

# Les variables


<div class="columns" style="--split: 1.2fr 1fr ">
<div>

* L'utilisation de variables est une bonne pratique permettant de modifier rapidement une modélisation.
* Lorsque la variable est modifié les changements sont appliqués en cascades aux sketchs et aux formes 3D construites à partir des skectchs.

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

# Mode solide

- Parts
- Extrusion : join / remove / new body /
- Extrusion / révolution / balayage
- Opération booléenne sur les body
- Chanfrein
- Esquisse depuis une face
- Symétrie / réseaux

---


<!-- _class: title -->
# ***Bonnes pratiques de modélisation***
# ***pour l'impression 3D***

---

# Bonnes pratiques de modélisation pour l'impression 3D

- Eviter les overhangs
- Penser aux tolérences
- Volume d'impression
- Taille des parois
- penser à l'orientation sur le bed (exemple de la maison poly pocket)

---

# Vérifier sa modélisation

- Inspection 
- Vu de section

---

<!-- _class: title -->
# ***Un peu de pratique***

---

# Exercice 1 : 

- Extrusion


---

# Exercice 2 :
