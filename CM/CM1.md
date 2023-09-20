---
marp: true
paginate: true
class: slide
theme: khoarau
---

<!-- _class: title -->
![bg left:40% 80%](images/cm1/3dprinterold.jpg)
# ***CAO pour l'impression 3D***
## Introduction à l'impression 3D
Kévin Hoarau - Septembre 2023

---

# La fabrication additive

<div class="columns" style="--split: 1.5fr 1fr ">
<div>

* L'impression 3D est une méthode de **fabrication additive**
* Elle s'oppose aux méthodes de fabrication soustractive ou de moulage, très largement employé dans l'industrie.
* Permet un prototypage rapide et à faible coût

</div>
<div>  

![](images/cm1/manufacturing.webp)
<div class="image_caption">"How Can 3D Optical Profiling Optimize Additive Manufacturing Processes?", Azom.com</div>

</div>
</div>

---

# Histoire de l'impression 3D grand public

<div class="columns" style="--split: 1.5fr 1fr ">
<div>

<!--* 1988 : Brevetage de la technologie SLS (*Selective Laser Sintering*)-->
* 1988 : Brevetage de la technologie FDM (*Fused Deposition Modeling*)
* 2005 : Le projet RepRap est lancée par Adrian Bowyer (Université de Bath, Royaume-Uni)
* 2008 : La "Darwin" produit une réplication complète d'elle-même (pièces imprimables)
* 2009 : Le brevet sur la technologie FDM expire

</div>
<div>  

![h:400 center](images/cm1/darwin.jpg)
<div class="image_caption">RepRap 1.0 "Darwin"</div>

</div>
</div>

---

# Histoire de l'impression 3D grand public

<div class="columns" style="--split: 1.2fr 1fr ">
<div>

* 2009 : Josef Prusa simplifie la RepRap Mendel et crée la Prusa Mendel
"Le modèle Prusa est la Ford T des imprimantes 3D."(Reprap.org)
* 2015 : Commercialisation de la Prusa i3
* 2016 : K. Hoarau construit une imprimante 3D approximative avec des chutes de bois
* 2018 : Commercialisation de la Creality Ender 3 à moins de 200€

</div>
<div>  

![center](images/cm1/prusa_farm.jpg)
<div class="image_caption">Ferme d'impression Prusa</div>

</div>
</div>

---

# Technologies d'impression 3D

<div class="columns" style="--split: 1.8fr 1fr ">
<div>

## Fused deposition modeling (FDM)

* La technologie FDM ou DFF (dépôt de fil fondu) est la plus répandue. 
* Elle consiste à faire fondre un filament de matière polymère puis à déposer cette matière couche par couche.


</div>
<div>  

![center](images/cm1/FDM_printing_diagram.svg)
<div class="image_caption">"Procédé Fused Deposition Modeling (FDM)", Wikipedia</div>

</div>
</div>

---

# Technologies d'impression 3D

<div class="columns" style="--split: 1fr 1fr ">
<div>

## La photopolymérisation

*  Les imprimantes SLA (*StereoLithography Apparatus*) utilisent un balayage laser pour solidifier une résine sensible aux UV
* Les imprimantes DLP (*Digital Light Processing*) utilisent un projecteur permettant de solidifier une couche entière 

</div>
<div>  

![center w:1000](images/cm1/DLP-and-SLA-FInal-Image.webp)
<div class="image_caption">"The Difference between DLP and SLA 3D Printing Technology",  MANUFACTUR3D</div>

</div>
</div>


---

# Anatomie d'une imprimante FDM


<div class="columns" style="--split: 2fr 1fr ">
<div>

## Châssis (*Frame*)

* La structure la plus répandue est l'imprimante cartésienne
* Le châssis est généralement formé à partir d'extrusions métalliques
* Les axes X et Y sont actionné par un système de couroies (meilleure vitesse et acceleration)
* L'axe des Z est actionné par une vis sans fin (meilleur couple)


</div>
<div>  

![center w:1000](images/cm1/frame.drawio.svg)
<!--<div class="image_caption">"The Difference between DLP and SLA 3D Printing Technology",  MANUFACTUR3D</div>-->

</div>
</div>

---

# Anatomie d'une imprimante FDM

<div class="columns" style="--split: 2fr 1fr ">
<div>

## Moteur pas à pas (*stepper motor*)

* Les moteurs pas à pas (Nema 17), sont utilisé par déplacer les différents axes (et l'extrudeur)
* Ce type de moteur permet de contrôler précisément leurs vitesses et positions 
* Pour cela, seul un capteur de fin de course est nécessaire sur chaque axe pour initialiser la position $X=0;Y=0;Z=0$ (*home position*)

</div>
<div>  

</br>

![center w:1000](images/cm1/nema17.jpg)
<div class="image_caption">Exemple de moteur NEMA 17 </br>200 pas/révolutions</div>

</div>
</div>

---

# Anatomie d'une imprimante FDM


<div class="columns" style="--split: 1fr 1fr ">
<div>

## La tête d'impression (*hotend*)

* C'est la pièce centrale qui est chargée de faire fondre le filament
* En fonction de la buse installée, le diamètre de sortie du fil fondu varie (généralement 0.4mm)
* C'est le bloc de chauffe, équipé d'une cartouche de chauffe et d'une thermistance qui permet de controller la température de la buse


</div>
<div>  

![center w:1000](images/cm1/hotend.png)
<div class="image_caption">http://wikifab.hatlab.fr</div>

</div>
</div>

---

# Anatomie d'une imprimante FDM


<div class="columns" style="--split: 2fr 1fr ">
<div>

## Extrudeur (*extruder*)

* L'extrudeur à pour rôle de pousser le filament vers la tête d'impression
* Une roue dentée montée sur un moteur pas à pas permet d'agripper le filament et de contrôler la vitesse d'extrusion
* Un extrudeur est dit *direct drive* lorsque qu'il est monté très proche de la tête d'impression

</div>
<div>  

![center w:1000](images/cm1/direct_drive.png)
<div class="image_caption">Extrudeur direct drive</div>

</div>
</div>

---

# Anatomie d'une imprimante FDM


<div class="columns" style="--split: 2fr 1fr ">
<div>

## Extrudeur Bowden

* Ce type d'extrudeur très répandu dans les imprimantes d'entrée de gamme
* Le moteur de l'extrudeur y est déporté sur le chassis et un tube PTFE guide le filament jusqu'à la tête d'impression
* Il permet de réduire la masse en mouvement
* Cependant, il est peu adapté aux filaments flexibles

</div>
<div>  

![center w:1000](images/cm1/bowden.webp)
<div class="image_caption">Extrudeur Bowden</div>

</div>
</div>


---

# Anatomie d'une imprimante FDM


<div class="columns" style="--split: 1.5fr 1fr ">
<div>

## Plateau chauffant (Heated Bed)

* Le plateau est la surface sur laquelle la pièce va être imprimer
* La partie chauffante permet de contrôler la température du plateau afin d'éviter le collement de la pièce durant l'impression
* Un support est généralement utilisé, son rôle est notamment d'améliorer d'adhérence durant l'impression et de faciliter le retrait de la pièce post-impression.


</div>
<div>  

![center w:1000](images/cm1/heatbed.jpg)
<!--<div class="image_caption">"The Difference between DLP and SLA 3D Printing Technology",  MANUFACTUR3D</div>-->

</div>
</div>

---

# Anatomie d'une imprimante FDM


<div class="columns" style="--split: 1.5fr 1fr ">
<div>

## Carte mère (*controller board*)

* Elle chargé de piloter l'ensemble des composants de l'imprimante
* Elle interprète les instructions envoyé par un ordinateur ou contenu dans un fichier
* Parfois il est possible de changer les contrôleurs des moteurs pas à pas



</div>
<div>  

![center w:1000](images/cm1/motherboard.webp)
<div class="image_caption">Ramps 1.4</br>(Reprap Arduino Mega Pololu Shield)</div>

</div>
</div>

---

# Anatomie d'une imprimante FDM


<div class="columns" style="--split: 1.5fr 1fr ">
<div>

## Contrôleur pas à pas (*stepper driver*)

* Ce circuit est dédié au pilotage d'un moteur à pas.
* Le A4988 était le plus utilisé dans les premières imprimantes 3D grand public. Il permet un microstepping de 1/16.
* Le TMC2208 permet un microstepping de 1/256 rendant l'opération du moteur beaucoup plus silencieuse.

</div>
<div>  

<br>

![center w:1000](images/cm1/A4988.jpg)
<div class="image_caption">Contrôleur A4988</div>

</div>
</div>

---

# Autres

Bed leveling : manuel ou assisté
Impression multi-materiaux/multi-color

---

# Delta vs core xy etc

---

# Les matériaux

---

# Chaine de production

CAO
Slicer
Impression

---

# Les outils de base

- Pied à coulisse
- Spatule
- Pince à epiler
- Pince coupante


--- 

# CAM

gcode