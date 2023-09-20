---
marp: true
paginate: true
class: slide
theme: khoarau
---

<!-- _class: title -->
![bg left:40% 80%](images/cm2/yoda.png)
# ***CAO pour l'impression 3D***
## Préparation d'une impression 3D
Kévin Hoarau - Septembre 2023

---

<!-- header: CAO pour l'impression 3D -->
<!-- _class: title -->
# ***Entretien de l'imprimante***

---

# Changement du filament

Il existe générelement une option sur l'interface de l'imprimante lancer une procédure de changement de filament. Cela déclanche généralement la commande GCODE `M600`.

Cependant, il est parfois plus simple de faire le changement manuellement, la procédure à suivre est alors :
1. Chauffer la tête d'impression (200° C pour le PLA)
2. Couper le bout du filament à insérer en biais
3. Détendre le mécanisme de serrage de l'extrudeur pour y insérer le filament
4. Insérer le filament jusqu'a que la nouvelle couleur soit bien nette en sortie de buse 

---

# Nivellement du plateau

<div class="columns" style="--split: 1.8fr 1fr ">
<div>

* Le nivellement du plateau est probablement le critère le plus important pour la réussite d'une impression
* Il doit toujours être fait à chaud, car le plateau se déforme sous l'effet de la chaleur
* Pour la majorité des imprimantes le nivellement doit être fait à la mains en ajustant des écrous aux quatre coins du plateau
* L'espace entre le plateau et la tête d'impression doit être de l'épaisseur d'une feuille de papier.

</div>
<div>  

<br>

![center](images/cm2/bed_leveling.png)
<div class="image_caption">"3D Printing Essentials: How to Perfectly Level your Bed", MatterHackers</div>

</div>
</div>

---

# Nettoyage du plateau

<div class="columns" style="--split: 2fr 1fr ">
<div>


* Pour garantir une bonne adhérence des impressions, il est important d'avoir un plateau propre
* En fonction du revêtement, la manière de nettoyer un plateau peut changer
* Généralement, un nettoyage à l'eau savonneuse ou à l'IPA donnent de bons résultats

</div>
<div>  

<br>

![center w:300](images/cm2/clean_bed.webp)
<div class="image_caption">filimprimante3d.fr</div>

</div>
</div>

--- 

# Problème fréquent avec les extrudeurs Bowden

<div class="columns" style="--split: 2.5fr 1fr ">
<div>

* Il arrive souvent avec les imprimantes de type Bowden que le filament casse entre l'extrudeur et la tête d'impression
* Cela rends alors impossible de changement du filament et détériore les impressions (pas de rétractation)
* Pour résoudre ce problème il faut tout d'abord chauffé la tête d'impression puis dévisser le raccord pneufit afin de récupérer le filament cassé 
* Vous pouvez utiliser un bon de filament pour pousser les morceaux hors du tube PTFE

</div>
<div>  

<br>

![center w:250](images/cm2/pneufit.jpg)

</div>
</div>

---

# Quelques mots sur la sécurité

<div class="columns" style="--split: 2.5fr 1fr ">
<div>

* Ne pas laisse une imprimante sans surveillance. A minima, on utilisera une caméra IP avec la possibilité d'interrompre l'impression à distance.
* Toujours surveiller la première couche ! S'il n'a première couche n'adhère pas bien alors vous pouvez interrompre de suite l'impression.
* Attention avec la spatule, elle est très coupante. 
* Evidemment ne pas toucher la buse avec les doigts. On utilise une pince à épiler pour retirer les filaments accrochés.

</div>
<div>  

<br>

![center w:250](images/cm2/spatule_danger.jpg)
<div class="image_caption">Ne jamais placer sa main devant la spatule !</div>

</div>
</div>

---

<!-- _class: title -->
# ***Paramétrage de l'impression dans un Slicer***

---

# Le slicer

* L'utilisation d'un *slicer* est une étape indispensable d'un processus d'impression 3D.
* Ce logiciel à pour rôle de transformer un objet 3D, généralement au format STL, en une suite d'instructions compréhensibles par une imprimante 3D (G-code).
* Une étape intermédiaire est le tranchage de l'objet en plusieurs couches de hauteur fixe, d'où le terme *slicer*.

![center h:230](images/cm2/poly.drawio.svg)

---

# Un mot sur le G-code

* Le G-code est un langage de programmation très largement utilisé par les machines-outil à commande numérique ou CNC (*computer numerical control*).
* Les imprimantes 3D tout comme de nombreuses graveuses/découpeuses laser ou fraiseuses numériques sont pilotées par des commandes G-code.
* Il est possible de lire et/ou modifier le G-code produit par le slicer à l'aide d'un éditeur de texte.
* Par exemple, vous pouvez manuellement rajouter la commande `M600` à partir d'une certaine couche afin de changer de couleur de filament.

---

# Quel slicer choisir ?

* Il existe un grand choix de slicer, certains sont open-source, d'autres sont propriétaire mais gratuit et certains sont payants.
* La plupart des slicers offrents de fonctionnalités et parametrages de base similaires
* Votre choix doit donc se faire en fonction de vos critères financiers, ergonomique, fonctionnalités avancées, *etc*
* Dans ce cours j'utiliserai UltiMaker Cura qui est open source.

---

# Comment paramétrer son impression 3D ?

<div class="columns" style="--split: 2.5fr 1fr ">
<div>

* Il existe un grand nombre de paramètres qui peuvent ajuster en fonction de la pièce à imprimer
* Les slicers modernes proposent pour la plupart des paramètres de bases pour bon nombre de modèles d'imprimantes
* On recommande généralement, de partir des paramètres de bases proposé par le slicer et d'ajuster certains entre-eux en fonction de l'impression à produire ou du résultat obtenu sur l'impression

</div>
<div>  

<br>

![center w:250](images/cm2/slicer_settings.png)
<div class="image_caption">Extrait des parèmetres d'impression dans Cura</div>

</div>
</div>

---

<!-- _class: title -->
# ***Paramètres importants***

---

# Températures

<div class="columns" style="--split: 2.5fr 1fr ">
<div>

* Ces paramètres sont à définir en fonction du matériau utilisé
* Par exemple, pour le PLA la température de la tête d'impression devrait être configuré autout de 200°C et celui du plateau aux alentour de 60°C.
* On peut légèrement augmenter la température de la tête en cas de sous extrusion ou la baisser si on observe beaucoup de *stringing*

</div>
<div>  

<br>

![center w:250](images/cm2/stringing.jpg)
<div class="image_caption">Exemple de stringing</br>simplify3d.com</div>

</div>
</div>

---

# Hauteur de couche

<div class="columns" style="--split: 1.5fr 1fr ">
<div>

* Ce paramètre défini la hauteur des couches générées par le slicer.
* La valeur par défaut est généralement 0.2mm.
* On peut baisser cette valeur si la pièce comporte des détails très fins ou l'augmenter pour réduire le temps d'impression.
* Elle doit être choisie de manière à être proportionnel aux nombres de pas du moteur. Par exemple, pour une imprimante Creality : `0.12,0.16,0.20,0.24,0.28`

</div>
<div>  

![center w:1000](images/cm2/layer_height.png)
<div class="image_caption">Calculateur Prusa Research</div>

</div>
</div>

---

# Remplissage

<div class="columns" style="--split: 4fr 1fr ">
<div>

Pour économiser du plastique, on laisse souvent beaucoup de vide dans le remplissage d'une impression.

Deux paramètres sont à considérer :
* Le motif de remplissage défini la forme du remplissage. On optera généralement pour un motif tri-dimensionnel (cubique, gyroïde, *etc*) pour ces meilleurs propriétés mécaniques

* Le pourcentage de remplissage est généralement choisi entre 10% et 20%. Cependant, il peut être augmenté pour obtenir une pièce plus solide.

</div>
<div>  

![center w:1000](images/cm2/cubic_20.png)
<div class="image_caption" style="padding-bottom:10px">Cubique à 20%</div>

![center w:1000](images/cm2/cubic_10.png)
<div class="image_caption">Cubique à 10%</div>

</div>
</div>

---

# Epaisseur de la coque

<div class="columns" style="--split: 4fr 1fr ">
<div>

Il peut être utile d'épaissir la coque de la pièce afin de la rendre plus solide sans augmenter le remplissage.

Pour cela, les paramètres à modifier sont :
* Le nombre de parois
* Le nombre de couches supérieures et inférieures 

</div>
<div>  

![center w:1000](images/cm2/wall_2.png)
<div class="image_caption" style="padding-bottom:10px">2 parois</div>

![center w:1000](images/cm2/wall_4.png)
<div class="image_caption">4 parois</div>

</div>
</div>

---

<div class="columns" style="--split: 4fr 1fr ">
<div>

# Adhésion au plateau

Pour certaines pièces ou certains matériaux, il peut être utile d'augementer la surface de contact avec le plateau.

Deux paramètres peuvent être utilisés :
* L'utilisation d'une bordure permet ajouter une surface d'adhérence autour de la pièce.
* Le radeau imprime plusieurs couches d'interface avant d'imprimer la pièce au-dessus de ces couches.

</div>
<div>  

![center w:1000](images/cm2/ni_bordure_ni_radeau.png)
<div class="image_caption" style="padding-bottom:10px">Piece d'origine</div>


![center w:1000](images/cm2/bordure.png)
<div class="image_caption" style="padding-bottom:10px">Bordure</div>

![center w:1000](images/cm2/radeau.png)
<div class="image_caption">Radeau</div>

</div>
</div>

---

# Eviter le stringing

Ventilation de la piece
Rétractation

Voir troubleshooting guide


---


<!-- _class: title -->
# ***Les supports***

---
 
# Pourquoi mettre des supports

---

# Parametres

---

# Comment éviter les supports

---

# Quand mettre des supports

Overhang
Pontage

---

# Support

Interface
Support arborescent 
Placement manuel

---

# Orientation

Support
Contraintes mécaniques
Surface de contact avec le plateau

---

# Comment reduire les temps d'impression ?

Hauteur de couche
Infill
Nb Perimetre

---

# Comment décoller l'impression


---

# Post-processing

Poncage
Epoxy
Pistolet à air chaud
Ebavureur


---

# Comment faire adherer les pieces au plateau

---

# Ajouter une pause / Changer de filament en cours d'impression

---

Bed leveling
Manuel vs assisté

--- 

# Lancer l'impression

Via cura
Via carte sd
Interface web de l'imprimante
Octoprint