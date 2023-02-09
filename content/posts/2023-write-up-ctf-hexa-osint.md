---
title: "Retour d'expérience sur le CTF HEXA OSINT 2023"
date: 2023-02-07
draft: false
series  : "Write-ups"
tags: ["HEXA","CTF"]
---
<img src="/images/2023-HEXA/1500x500.jpg" alt="Logo du CTF" width="525" height="175" class="jop-noMdConv">

Du 27 au 29 janvier 2023 s'est déroulée la seconde édition du CTF (Capture The Flag) HEXA OSINT soutenu par [Sopra Steria](https://www.soprasteria.com/fr). Comme durant [la première édition fin 2021](https://portail-ie.fr/analysis/3023/retour-dexperience-challenge-hexa-osint-ctf "retour CTF 2021"), les équipes composées de quatre personnes maximum se sont mobilisées tout le week-end pour résoudre la disparition d'une certaine Lucilhe Dumarquais (personnage fictif) à partir de challenges OSINT riches & variés.

L'objectif de ce retour d'expérience est de revenir sur ceux-ci en détaillant la méthodologie mise en place et les difficultés rencontrées. Ce billet se place du point de vue de son auteur, encore néophyte dans le domaine. La méthodologie n'est ainsi pas toujours optimale, loin s'en faut, et ouverte à discussions.

Pour ce premier CTF à titre personnel, j'ai préféré découvrir à mon rythme en formant donc une "équipe de un". L'aspect collaboratif a clairement manqué à certains moments et aurait permis d'aller probablement un peu plus loin. Au final, je suis tout de même parvenu à résoudre une majorité des challenges avec 5810 points au total (16ème au classement général) avec la frustration de ne pas être parvenu à atteindre la partie analyse (à un challenge prêt ... si loin, si proche).

Last but not least, merci aux organisateurs pour l'intrigue, les challenges bien ficelés et le support tout au long du week-end : [@IWH - Clément CHESNEAU](https://fr.linkedin.com/in/cl%C3%A9ment-chesneau-0a8730133 "Clément CHESNEAU") / [@ALS - Adrien GUILLERME](https://fr.linkedin.com/in/adrien-guillerme "Adrien Guillerme") / [@TheBaboon - Esteban BOUILLARD](https://fr.linkedin.com/in/esteban-bouillard-b32196134 "Estebn Bouillard").

Plus d'infos : [site du HEXA CTF](https://hexactf.ctfd.io "Site HEXA") / [Twitter](https://twitter.com/HEXAOSINT "twitter HEXA OSINT ") / [Discord](https://t.co/aNSTXlwVA7 "Discord HEXA OSINT ")

* * *

## Intro

### Welcome back 

10 points - *Dear agents, You provided an outstanding work with the Manipar case just over a year ago. This group of activists, who met on Erasmus, stole data from sensitive sectors (bank, healthcare, military), to resell them to the highest bidders. With their arrest, this case is therefore closed. However, their leader, Lucilhe Dumarquais disappeared during a transfer. She intended to reveal more information about collaborating criminal organizations. Since then, there is no trace of her.*

*The investigation reached a dead end. The minister asked to carry on. Given your knowledge of the case, you are assigned to take over and understand this disappearance.*
***
## The Intruder

### The intruder

100 points - *We suspect a detective to be investigating the same case as us. He has a bad habit of trying to retrieve our information, so he could be among you. We know that he regularly creates YouTube channels during these investigations. Can you find the ID of his current YouTube channel? Something that may help: he usually pay tribute to a detective born in 1819, using his name as pseudonym.*

Le pseudonyme utilisé est obtenu par une simple recherche Google sur détective et l'année de naissance donnée, il s'agit d'Allan Pinkerton. Après avoir mal interprété la consigne et passé quelques temps à tourner autour des chaînes YouTube avec "Pinkerton", l'évidence apparaît : "*he could be among you*."

Une recherche sur "pinkerton" sur la plateforme du CTF permet de retrouver le bon profil, menant à sa [chaîne YouTube](https://www.youtube.com/channel/UCjyLqrOsjkpsMhczlbHJoFA "YouTube Pinkerton91") avec l'ID pour flag : 

<img src="/images/2023-HEXA/2023-01-30 22_32_23-HEXA OSINT CTF V2 — Mozilla Fi.png" alt="2023-01-30 22_32_23-HEXA OSINT CTF V2 — Mozilla Firefox.png" width="722" height="182" class="jop-noMdConv">

### Infiltration 

100 points - *This guy is too well informed to work alone. He has to have a way to communicate with his associates. Can you find it?*

Sur la [chaîne YouTube](https://www.youtube.com/channel/UCjyLqrOsjkpsMhczlbHJoFA) précédemment évoquée, on peut trouver des vidéos format "Shorts" dont l'une avec un username TikTok dessus :

<img src="/images/2023-HEXA/2023-01-30 22_36_23-(14) Pinkerton - YouTube — Moz.png" alt="2023-01-30 22_36_23-(14) Pinkerton - YouTube — Mozilla Firefox.png" width="624" height="330" class="jop-noMdConv">

En pivotant sur le Tiktok en question, la description mène vers le Discord du détective Pinkerton :

*<img src="/images/2023-HEXA/2023-01-30 22_59_54-user545947198194 (@user5459471.png" alt="2023-01-30 22_59_54-user545947198194 (@user545947198194) _ TikTok — Mozilla Firefox.png" width="226" height="304" class="jop-noMdConv">*

Le flag est sur la page d'accueil :

<img src="/images/2023-HEXA/2023-01-30 23_03_52-_harfang _ Serveur de J. Pinke.png" alt="2023-01-30 23_03_52-#harfang _ Serveur de J. Pinkerton - Discord.png" width="759" height="258" class="jop-noMdConv">

La suite de la branche "The Intruder" est un ensemble d'indices à mettre bout à bout à partir du Discord en question. Chaque challenge validé sur le Discord, donne une partie de la commande qui une fois concaténée avec les autres permet d'avancer au niveau suivant. La commande permet également de valider le challenge correspondant au niveau du CTF.

### Sneak beak

200 points - *Great, you found the server! The detective seems to be looking for help. We need you to obtain the upper roles he is talking about. Start by gaining the next role after the Cheveche role.*

Pour commencer #chevêche, J.Pinkerton nous donne deux challenges à resoudre :

*<img src="/images/2023-HEXA/2023-01-30 23_02_38-_chevêche _ Serveur de J. Pink.png" alt="2023-01-30 23_02_38-#chevêche _ Serveur de J. Pinkerton - Discord.png" width="644" height="381" class="jop-noMdConv">*

1\. Un MP3 d'un homme chantonnant, on semble distinguer les termes "I know" et "Catolina". Rien coté métadonnées. La recherche de ces paroles sur Google ne donne aucun résultat pertinent. Les autres options écartées, la piste paraît logique : trouver un outil permettant de retrouver une chanson à partir d'un chantonnement. 

Cela mène à [Google Search, et son option de reconnaissance audio,](https://blog.google/products/search/hum-to-search/ "Google Search Audio") en sélectionnant spécifiquement le mode chanson. En jouant le .mp3, l'outil sort comme premier résultat la chanson "LEMONADE" du groupe "bonobos" :

<img src="/images/2023-HEXA/Screenshot_2023-01-30-23-40-39-080_com.google.andr.jpg" alt="Screenshot_2023-01-30-23-40-39-080_com.google.android.googlequicksearchbox.jpg" width="344" height="378" class="jop-noMdConv">

En effectuant une vérification [sur YouTube](https://www.youtube.com/watch?v=sSO2mplFn-Q), il s'agit bien de la chanson de la voiture.

2\. *En France, quel article du code pénal traite de l'usurpation d'identité ?* 

Le fait d'être natif permet déjà d'avoir une idée assez claire d'où chercher. La combinaison "usurpation d'identité légifrance" mène directement à l'[article 226-4-1 du code pénal](https://www.legifrance.gouv.fr/codes/article_lc/LEGIARTI000042193593) :

<img src="/images/2023-HEXA/2023-01-31 11_36_52-Article 226-4-1 - Code pénal -.png" alt="2023-01-31 11_36_52-Article 226-4-1 - Code pénal - Légifrance — Mozilla Firefox.png" width="887" height="185" class="jop-noMdConv">

### Grow older

300 points - *Well done, you obtained the Hulotte role. Please try to move forward and gain access to the next channel with the Effraie role.*

*<img src="/images/2023-HEXA/2023-01-30 23_02_47-_hulotte _ Serveur de J. Pinke.png" alt="2023-01-30 23_02_47-#hulotte _ Serveur de J. Pinkerton - Discord.png" width="548" height="374" class="jop-noMdConv">*

3\. "Europe", "Loi", "Données personnelles" : tout mène vers le RGPD. Il reste à retrouver l'[article 17 qui traite de la suppression de données](https://www.cnil.fr/fr/reglement-europeen-protection-donnees/chapitre3#Article17) (droit à l'oubli).

4\. Après quelques recherches et calculs infructueux sur le [site gouvernemental de l'U.S Bureau of Labor Statistics,](https://www.bls.gov/ "US Bureau of Labor Statistics ") je tente la recherche "eggs inflation october november 2022" et tout simplement tombe le chiffre recherché depuis un [article sur Yahoo.com](https://finance.yahoo.com/news/eggs-other-foods-got-crazy-120057151.html "Yahoo Finance ") :  "The price of eggs jumped by 2.3% from October to November". 

5\. Une lecture attentive de l'intitulé fait ressortir d'abord "hotel in Veneto". Nous sommes en Italie et on recherche un hôtel qui donne sur l'Adriatique en Vénétie.

Le champ est large. Je recherche alors le terme qui doit se trouver dans l'angle de la caméra "fantasy". Sur la côte Adriatique, proche de la mer, une seule occurence ressort : "Pizzeria fantasy" dans la ville de Chioggia : 

<img src="/images/2023-HEXA/2023-02-03-fantasy.png" alt="Fantasy Pizza" height="385" class="jop-noMdConv">

On regarde depuis Streetview à quoi peut ressembler le panneau :

<img src="/images/2023-HEXA/2023-02-03 21_53_43-28 Lungomare Adriatico - Googl.png" alt="2023-02-03 21_53_43-28 Lungomare Adriatico - Google&nbsp;Maps — Mozilla Firefox.png" width="607" height="385" class="jop-noMdConv">

Maintenant, est-ce qu'il y a un hôtel qui pourrait voir ce panneau entre la caméra en question et le front de mer ? Cela semble plausible au niveau de l'hôtel le plus proche "Ambasciatori" : 

<img src="/images/2023-HEXA/2023-02-03 21_54_28-fantasy - Google Maps — Mozill.png" alt="2023-02-03 21_54_28-fantasy - Google&nbsp;Maps — Mozilla Firefox.png" width="346" height="389" class="jop-noMdConv">

Comment désormais retrouver la caméra pour bien valider le challenge ? 

En parcourant les images de clients, il semble bien fastidieux de retrouver l'élément concerné. À la relecture, le "*set on an hotel*" fait plutôt penser à une caméra type surveillance ou webcam. Il existe de nombreuses webcam publiques. 

En effectuant une recherche sur webcam + le nom de l'hôtel potentiel on parvient à [une webcam qui diffuse en direct](https://www.skylinewebcams.com/fr/webcam/italia/veneto/venezia/chioggia-sottomarina.html "webcam direct") le front de mer depuis l'hôtel. Le "fantasy" de la pizzeria est bien là également pour valider l'ensemble de l'énoncé. 

Une dernière recherche sur l'hôtel permet de retrouver son numéro de téléphone : 

<img src="/images/2023-HEXA/2023-02-03 22_16_03-hotel ambassitori chioggia - R.png" alt="2023-02-03 22_16_03-hotel ambassitori chioggia - Recherche Google — Mozilla Firefox.png" width="272" height="150" class="jop-noMdConv">

### Tell me owl your secrets

600 points *This is becoming interesting! You are already having new information on the case. We are approaching the goal, continue like this and try to get the Tengmalm role.*

*<img src="/images/2023-HEXA/2023-01-30 23_02_58-_effraie _ Serveur de J. Pinke.png" alt="2023-01-30 23_02_58-#effraie _ Serveur de J. Pinkerton - Discord.png" width="541" height="364" class="jop-noMdConv">*

6\. L'objectif est de retrouver le profil sur un réseau social de l'homme chantonnant au volant. On sait désormais qu'il s'appelle "Tsuzune Yokoyama". On trouvera son mail plus tard dans le challenge [Decentralized](#decentralized).

Les recherches sur Google ou [Whatsmyname](https://whatsmyname.app/) ne donnent rien de pertinent sur les réseaux sociaux habituels. Point important, il est précise que l'homme est japonais. Il ressort que le [réseau social le plus populaire au Japon](https://www.bigbeatinc.com/blog/japan_social_media_2022) est [Line](https://line.me/en/). 

J'installe cette chose sur un téléphone, et retrouve le profil de Tsuzune. En utilisant Google Lens pour traduire et après un rapide calcul (il aura 60 ans cette année), on obtient sa date de naissance : 21 / 03 / 1963 :

<img src="/images/2023-HEXA/2023-02-01 22_40_39-HEXA OSINT CTF v2 (2023) Write.png" class="jop-noMdConv">

7\. Je suis ce [tutoriel pour récupérer l'ID Discord d'un utilisateur](https://www.journaldufreenaute.fr/comment-trouver-lidentifiant-id-discord/) : d'abord autoriser le mode développeur dans son app,  ensuite réaliser un clic droit sur l'identité du concerné (ici el famoso J.Pinkerton) et copier l'identifiant :

<img src="/images/2023-HEXA/2023-02-01 22_30_36-_effraie _ Serveur de J. Pinke.png" alt="2023-02-01 22_30_36-#effraie _ Serveur de J. Pinkerton - Discord.png" width="282" height="301" class="jop-noMdConv">

8\. Dans cette courte vidéo, on découvre deux éléments :

- le site du fabriquant qui fournit la solution réseau à l'entreprise dans l'industrie médicale recherchée : https://www.draytek.com/ .<img src="/images/2023-HEXA/2023-02-01 22_15_38-_effraie _ Serveur de J. Pinke.png" alt="2023-02-01 22_15_38-#effraie _ Serveur de J. Pinkerton - Discord.png" width="527" height="242" class="jop-noMdConv">
- une moitié finale d'adresse MAC notée sur papier :

<img src="/images/2023-HEXA/2023-02-01 22_15_47-_effraie _ Serveur de J. Pinke.png" class="jop-noMdConv">

Le challenge est donc de retrouver la moitié d'adresse manquante. Les trois premiers octets d'une adresse MAC désigne le constructeur. Les adresses liées à DrayTek sont [disponibles depuis ce site](https://udger.com/resources/mac-address-vendor-detail?name=draytek_corp "DrayTek MAC"). Il nous donne donne trois possibilités : 00:1D:AA / 00:50:7F / 14:49:BC.

Pour trouver le SSID souhaité, nous allons ensuite utiliser [https://wigle.net/](https://wigle.net/ "Wigle"), site collaboratif qui listes les points d'accès Wi-Fi et antennes-relais dans le monde. Je vais alors tenter les trois combinaisons possibles, le résultat positif tombe pour l'adresse 00:1D:AA:9E:A9:75 :

<img src="/images/2023-HEXA/2023-01-28 21_52_54-WiGLE_ Wireless Network Mappin.png" class="jop-noMdConv">

Le nom du SSID à transmettre est "LGNhealthinovativeltv-guest".

### Owlmost there

900 points  - *Good job! You got the Tengmalm role and it looks like "serious business". The Grand-duc role may be the last one. Pursue your effort and try to get it.* 

*<img src="/images/2023-HEXA/2023-01-30 23_03_09-_tengmalm _ Serveur de J. Pink.png" alt="2023-01-30 23_03_09-#tengmalm _ Serveur de J. Pinkerton - Discord.png" width="532" height="398" class="jop-noMdConv">*

**NON VALIDÉ** : pas de pistes pour les challenges 10 & 11, j'ai préféré me concentrer sur d'autres challenges en espérant y revenir plus tard (et puis en fait non 😒).

***

## Action Man

### Hijacking

<img src="/images/2023-HEXA/Hijacking.JPG" alt="Hijacking.JPG" width="232" height="264" class="jop-noMdConv">

*The convoy transporting Lucilhe from "Maison d'arrêt de Versailles" was hijhacked on the 30th of November 2022. She has not been seen since and her case file is incomplete. A tiny mistake has been made: the picture of the convoy's destination was provided but not the place's name. Please begin by completing the file with the name of this convoy's destination.*

Une recherche inversée sur l'image permet d'arriver au [Tribunal Judicaire de Versailles](https://www.cours-appel.justice.fr/versailles/tribunal-judiciaire-de-versailles).

### Fast and Furious

*<img src="/images/2023-HEXA/FastandFurious.JPG" alt="FastandFurious.JPG" width="700" class="jop-noMdConv">*

*A witness saw a patrol vagon driving at top speed. We think it was the one carrying Lucilhe. Can you retrieve the road's name where the picture was taken from?*

On devine une intersection, avec plusieurs directions, une ligne de tram, et différentes panneaux directionnels.

 À partir de ceux-ci, on identifie la direction de l'hôtel de ville et "Le Village" (éléments proches) et d'une départementale menant à Meudon (D57). La recherche sur Meudon et le suivi de la D57 permet d'avoir une idée globale d'où se situe la photo. 
 
 En remontant la départementale, on peut effectuer une recherche sur "Le village" dans la zone concernée. On parvient rapidement à repérer la configuration du lieu avec les éléments des panneaux. Un passage ensuite coté Streetview permet de confirmer et repérer la rue exacte de la prise de vue : 

<img src="/images/2023-HEXA/2023-02-03 13_17_50-Window.png" width="500" class="jop-noMdConv">

### Fly me to the moon

<img src="/images/2023-HEXA/Flymetothemoon.jpg" alt="Flymetothemoon.jpg" width="314" class="jop-noMdConv">

*We found the place where they were hiding after the hijacking. The attachements are evidences we found there. Can you find the city they were heading to?*

Il s'agit de papiers chiffonnés dans une poubelle, on y distingue deux éléments importants : un mail à destination d'un certain Oleg (qui s'avèrera être notre [Action Man](#action-man)) et un code FSF145P. 

La recherche sur ce code permet d'obtenir [le vol correspondant](https://airportinfo.live/fr/vol/fsf145p "Vol ") depuis Le Bourget (LBG) à Paris vers l'aéroport VIP. Il s'agit du [code pour l'aéroport de Payerne](https://www.iata.org/en/publications/directories/code-search/?airport.search=VIP "aéroport Payerne") en Suisse.

### Chocolate

<img src="/images/2023-HEXA/Chocolate.png" alt="Chocolate.png" width="700" class="jop-noMdConv">

*Using the data we found on the previous safehouse, we managed to retrieve a message sent weeks ago: "We arrived. It was necessary to use public transports, all the taxis were taken. Hurry up, I feel uneasy waiting here". This picture was attached. Find the street where they are waiting.*

Ce challenge m'a pris du temps ! On aperçoit des noms partiels de devantures ainsi qu'une ligne de tram. Coté devantures, deux éléments lisibles : "alle wo" qui semble correspondre à un restaurant avec sa terrasse et "etsch" suivi d'un drapeau Suisse. L'environnement global fait penser à un centre ville d'une certaine importance.

Ces éléments me font penser qu'[Action Man](#action-man) se trouve dans une ville de Suisse alémanique ("alle" avec pour hypothèse qu'il s'agit de halle vu le lieu type restaurant; "etsch" qui s'apparente aussi bien à la langue de Goethe).

À partir de la, mon hypothèse se porte sur Zürich ou Bâle, mais comment retrouver l'endroit exact ? La recherche sur les parties de noms ne donnent rien.

J'ai alors repensé au billet ["Comment géolocaliser une image ?"](https://degun.eu/posts/tutoriel-geolocalisation-image/ "Degun - géolocaliser une image ") de [Degun](https://www.linkedin.com/in/iamyoanblanc/ "Degun ") pour [Ozint.eu](https://ozint.eu), plateforme d'apprentissage dédiée à l'OSINT. L'outil [Overpass turbo](https://overpass-turbo.eu/ "overpass") est présenté pour l'exploration de données OpenStreetMap.

En partant sur "amenities=restaurant" et en effectuant la requête sur la zone de la ville en question. On obtient une liste importante de points. Pour restreindre un peu plus, il aurait été possible de configurer la requête afin de détecter les restaurants à proximité d'une ligne de tram.

Dans la partie "Données", en recherchant alors les lettres de la devanture "alle wo", on obtient le restaurant "Bierhalle Wolf". Après vérification sur Streetview, il s'agit bien du lieu de prise de la photo, rue Limmatquai.

<img src="/images/2023-HEXA/2023-01-31 21_06_54-overpass turbo — Mozilla Firef.png" class="jop-noMdConv">

### Tank Engine

*We found evidence of their passage in a safehouse in the previous location you've found. The most interesting one is a phone with a received message weeks ago from a contact named "action man": "We took a direct train connection from Zurich. The journey takes 03:07. Our contact also confirmed the appointment." In which city did this appointment take place?*

Toute la question est de trouver comment repérer précisément une durée de train entre deux lieux en ayant connaissance d'un seul ?

Les recherches ont rapidement menées vers [https://www.chronotrains.com/fr](https://www.chronotrains.com/fr "chronotrains") qui permet de sélectionner une gare et voir les durées de trajet par palier : 1h / 2h / 3h etc. Il n'est par contre pas possible de localiser un point précis, ainsi pas possible alors de repérer un 3h07.

Sur ce site est précisé "Cette carte est inspirée de [Direkt Bahn Guru](https://direkt.bahn.guru/). Les données proviennent de la Deutsche Bahn", ce lien va bien arranger mes affaires. <br>
En cherchant la couleur du palier concerné, il reste quelques possibles, un peu de patience et on arrive sur le temps de trajet de 3:07h juste pour la destination Zürich HB. > Cadenazzo :

<img src="/images/2023-HEXA/2023-01-31 12_19_27-Zürich HB _Directtrain.png" class="jop-noMdConv">

### Bonbon

<img src="/images/2023-HEXA/safehouse.jpg" alt="safehouse.jpg" width="332" height="220" class="jop-noMdConv">

*Another message with a picture was received from "action man" on the phone previously found, but more recently : "We drove few hours and took the boat. We arrived at the safehouse yesterday. We are about to head East. Still 142km to go until the airport near the fortress. Will be there for boarding in 3 days as planned." Can you find the airport where they boarded?*

Rien de notable à l'œil coté photo. Je me tourne rapidement vers les [métadonnées EXIF :](https://exiftool.org/ "EXIFTool")

<img src="/images/2023-HEXA/2023-02-01 17_23_47-D__Cyb_exiftool-12.48_exiftool.png" class="jop-noMdConv">

On y trouve des coordonnées GPS "35º 31' 1.82" N, 24º 1' 3.11" E" qui nous amène en Crète sur le port de La Canée.

Deuxième étape, il va falloir localiser l'aéroport à 142km à l'Est. Héraklion est à bonne distance à l'est, c'est la plus grande ville de l'île qui dispose donc surement d'un aéroport. L'itinéraire est d'exactement de 142Km. Ils ont embarqué à l'Aéroport international d'Héraklion Níkos-Kazantzákis.

<img src="/images/2023-HEXA/2023-02-01 17_30_18-Heraklion State Airport N. Kaz.png" alt="2023-02-01 17_30_18-Heraklion State Airport N. Kazantzakis à Vieux port vénitien, Ag. Markou 8, Chan.png" width="684" height="192" class="jop-noMdConv">

### Sovereign city

*We intercepted a new message from "action man" sent days ago: "We will land at way 646940106, then we plan to hide near node 1803847939. Before we leave the city, we will change our car near way 22762642. After that, relation 8810294 will allow us to leave the city by staying on the left lane." Find where they were hiding and the city they are heading to.*

Ici encore, le salut va venir de [https://overpass-turbo.eu/.](https://overpass-turbo.eu/ "overpass turbo") Il suffira de détailler la consigne d'Action Man dans l'outil et d'exécuter : 

<img src="/images/2023-HEXA/2023-02-01 16_30_51-overpass turbo — Mozilla Firef.png" class="jop-noMdConv">

Ils atterrissent d'abord à l'aéroport de Singapour (way : 646940106) :

<img src="/images/2023-HEXA/2023-02-01 16_29_16-overpass turbo — Mozilla Firef.png" alt="2023-02-01 16_29_16-overpass turbo — Mozilla Firefox.png" width="452" height="328" class="jop-noMdConv">

Ensuite, la planque se situe dans le quartier de Hougang (node : 1803847939) :

<img src="/images/2023-HEXA/2023-02-01 16_30_01-overpass turbo — Mozilla Firef.png" class="jop-noMdConv">

Avec la nouvelle voiture récupérée (way : 22762642), ils emprunteront ensuite la route depuis Woodlands Road (relation : 8810294), en continuant sur la voie de gauche on arrive à Johor Bahru en Malaisie.

<img src="/images/2023-HEXA/2023-02-01 16_30_45-overpass turbo — Mozilla Firef.png" alt="2023-02-01 16_30_45-overpass turbo — Mozilla Firefox.png" width="462" height="347" class="jop-noMdConv">

### Original

*We contacted interpol about "action man". They have a biography record about him, but it seems something erased and rewrote the biography report several times. Forensics team managed to recover 12 different files but could not determine which one was written by a human... WARNING : You have only one try to get the right answer*

On récupère 12 rapports sur Action Man, un seul est un original écrit par un humain. Une seule tentative possible, comment faire pour trouver le bon ?

J'ai d'abord ouvert les 12 rapports et essayé d'inspecter les différences en les parcourant. Premier élément, le manque de signature sur le numéro 10, une erreur HUMAINE ? Est-ce bien suffisant ? 

Ensuite, j'ai passé l'ensemble des rapports sur https://copyleaks.com/features/ai-content-detector. Ils sont revenus tous positifs, l'analyse ne parvenant pas à différencier les parties probablement.

Retour alors à l'analyse humaine en comparant les rapports, un élément ressort alors sur le numéro 8, le chapitre "Criminal History" est bien différent, beaucoup plus détaillé avec des éléments circonstanciés :

`O. Vokolski has been involved in criminal activity since the late 1990s. In the late 90's, his robberies, always very discreet and never leaving a trace, made him known as "Złodziej cieni" (the shadow thief). In 2000, he planned the Narodowy Bank Polski heist, but was arrested because one of his team members who was waiting outside the bank was recognized by a passer-by who alerted the police. He will not reveal any information about his plan or his accomplices. For this crimes, he was sentenced to 17 years in a maximum security prison. However, he managed to escape, and since then, he has not been found.`

Afin quand même de vérifier l'hypothèse, je reviens au [détecteur d'IA](https://copyleaks.com/features/ai-content-detector "détecteur IA") et passe chacun des 12 chapitres "Criminal History", le seul à sortir en "Human text" est bien ce rapport 8, challenge validé.

<img src="/images/2023-HEXA/2023-02-01 17_43_43-AI Content Detector _ AI Detec.png" alt="2023-02-01 17_43_43-AI Content Detector _ AI Detector - Copyleaks.png" width="625" height="214" class="jop-noMdConv">

### Final countdown 
*We just received another message from "action man" sent on the phone we found at the safehouse: "As planned, we are hiding in the building in zone 4. The religious man waited us there as planned. This isn't very secure, but it will do the job. We can't stay there more than a week, so find us a boat to reach the final location. We won't be able to reach the sea on foot from there (more than two kilometers by foot is more than the package can handle), so find us a car too... I expect news in a couple days. I scouted the environment on foot for five minutes and I talked with locals playing soccer on a field near the building. With some financial insentive, they will warn me if they see or hear anything that could compromise our position." This is a great opportunity to find where they are hiding. We have a chance to catch them, so give us this "building" OSM identifier so we can send a team.*

**NON VALIDÉ**

Le challenge le plus frustrant puisqu'il m'aurait permis de débloquer l'analyse.

Après avoir trouvé la zone 4, en utilisant le fichier "Zones.kmz" obtenus depuis le lien .onion du site de Mastermind (challenge [Herbaceous](#herbaceous)), j'ai utilisé encore une fois [Overpass turbo](https://overpass-turbo.eu/ "Overpass") pour déterminer les lieux avec un terrain de sport ouvert (leisure=pitch), et les lieux religieux (amenity=place\_of\_worship).

Mais je n'ai pas su bien optimiser la recherche [Overpass](https://overpass-turbo.eu/ "overpass") pour faire le lien "5 minutes d'un terrain" et proche d'un religieux, ce qui aurait permis de faire ressortir plus nettement le lieu recherché. Lors de la recherche "manuelle" sans conviction, j'ai ensuite fait l'erreur de me concentrer sur la zone autour des 2 kilomètres de la mer de l'énoncé.

* * *

## The Associate

### Contract

<img src="/images/2023-HEXA/2023-02-01 16_47_30-Contract.jpg ‎- Photos.png" width="300" class="jop-noMdConv">

*We found evidence of their passage in a safehouse in Zurich. The most interesting one is a phone configured in romansh with a received picture attached to a message. This message is from a contact named "associate". Can you find the location where the picture was taken?*

Un challenge marqué par un manque de vigilance ! J'ai d'abord commencé par chercher les informations EXIF liées à l'image. Sur le moment, je ne fais pas attention aux informations sur l'heure "UTC +4" qui est une aide importante.

Je repère rapidement les numéros sur la piste, il s'agit de runways "14-32". L'environnement général laisse penser à une destination ensoleillée, potentiellement une île vu la localisation de l'aéroport.

En effectuant une recherche inversée sur l'aile de l'avion, plusieurs résultats possibles, je me fixe un peu précipitamment sur Air Caraïbes (sans doute l'association avec le coté île précédemment supposé) et cherche alors ses destinations, en les croisant avec les numéros de runways (exports disponibles depuis [https://ourairports.com](https://ourairports.com "Our Aiports ")). Après avoir passé en revue l'ensemble des aéroports, rien à faire, pas de runways 14-32 sur les routes d'Air Caraïbes. 

Je comprends alors l'erreur : je n'ai pas été suffisamment attentif au moment de la recherche sur l'aile. C'est bleu aussi, mais il ne s'agit pas d'Air Caraïbes mais de Corsair. À partir de là, le résultat est rapide, je trouve les routes de la compagnie Corsair, ayant déjà vérifié la majorité des aéroports des Antilles (également désservies), je me tourne vers Port-Louis sur l'île Maurice et l'Aéroport Sir Seewoosagur Ramgoolam.

À partir de Google Maps, on retrouve bien la même configuration des numéros de runways, avec à l'horizon la mer, précédée par des maisons et un mont à proximité.

<img src="/images/2023-HEXA/2023-02-01 16_54_58-The Big Map @ OurAirports — Mo.png" width="700"  class="jop-noMdConv">

Les numéros de runways "14-32" sont confirmés par [https://ourairports.com](https://ourairports.com "Our Aiports ") :

<img src="/images/2023-HEXA/2023-02-01 16_53_55-Sir Seewoosagur Ramgoolam Inte.png" width="700"  class="jop-noMdConv">

### Impersonator

*We received a call from the contact "associate". The prefix of that number was 44. One of our agent answered the phone and the caller, a woman, told him : "Lian, it's me, I got the contract signed and I returned back at my place. Sell all your actions right now, the price is going to drop soon... Our system is getting more and more lucrative, it's a good thing. I hope the package is still on the way, our client is very influent worldwide, this could be useful... What is the current status?". Our agent tried to talk to the caller but she hang up, guess our agent isn't such a good impersonator... As the call did not last long, we managed get data of the triangulation but these data are incomplete. Can you help us to know what neighborhood she was calling from using the world's largest Open Database of Cell Towers?*
*Here are the data we managed to get :*
*Antena operator : EE (previously Orange S.A)*
*LAC : 11*
*Cell ID : 27855*

L'intitulé donne une information de comment chercher avec "world's largest Open Database of Cell Towers" : https://opencellid.org, les termes exacts sont sur la page d'accueil.

La zone de recherche est composée de quatre éléments : MCC (code de pays mobile) / MNC (code de réseau mobile) / LAC (indicatif régional) / Cell ID (identifiant de cellule) . <br>
Coté "LAC" et "Cell ID", il suffit de reprendre les éléments de l'intitulé. Ensuite pour "MCC" et "MNC", une recherche sur leurs significations mène notamment à https://mcc-mnc-list.com/list permettant de les identifier. 

Avec le préfixe +44, on sait qu'il s'agit d'un numéro en provenance du Royaume-Uni. On connait également l'opérateur "EE (précedemment Orange S.A)". En filtrant par pays, puis en recherchant l'opérateur, deux possibilités :

<img src="/images/2023-HEXA/2023-01-31 10_56_56-Complete up to date MCC MNC li.png" class="jop-noMdConv">

Le MCC est 234, le MNC soit 33 ou 34, le second ne donnant aucun résultat, le MNC = 33 mène à une antenne à Londres, dans le quartier de Chelsea :

<img src="/images/2023-HEXA/2023-01-31 10_59_09-OpenCelliD - Largest Open Data.png" alt="2023-01-31 10_59_09-OpenCelliD - Largest Open Database of Cell Towers &amp; Geolocation - by Unwired Lab.png" width="800" class="jop-noMdConv">

### Setup

*Our forensics team dug into the telephone and found a deleted message sent to "associate" : "Hey dear, remember the gift you offered me few years ago? It just stopped working... I'm so sad, your gifts are always plain but they fulfil me with joy. I will take it to the watchmaker ASAP, promise !". This watch could help us understand his definition of "plain", help us find the exact reference of the watch*

À partir d'une recherche d'image inversée, on obtient rapidement la référence, maintenant il existe plusieurs variantes, l'aspect doré correspond à la Festina F20286/3.

*<img src="/images/2023-HEXA/setup_montre_zoom.jpeg" alt="setup_montre_zoom.jpeg" width="235" height="245" class="jop-noMdConv">*

Autre élément semblant notable à partir de la photo (mais non utilisé ensuite de mon coté), en retournant l'image on peut remarquer une liste d'individus liés à Mastermind avec un alias "MastermindAlly3743" :

<img src="/images/2023-HEXA/2023-01-31 20_26_22-setup-2.jpeg ‎- Photos.png" alt="2023-01-31 20_26_22-setup-2.jpeg ‎- Photos.png" width="475" height="454" class="jop-noMdConv">

* * *

## Sidequest

### He is back 

300 points - *A collegue you haven't seen in a year runs into your office screaming : "IT WAS THE WRONG KERMIT!!!! The one I'm looking for is the third of his name and he had a grandparent who wrote something just after the great war. There is something interesting in his second novel, about the actor he will see to take the role of the main character in a movie theater". He vanishes before you can even open your mouth to talk with him. Maybe you can find the actor he was talking about..*

Un challenge à bien décomposer ! Je suis d'abord parti sur le fait que la recherche porte sur un "Kermit", celui-ci étant le troisième du nom. Il faut donc chercher un "Kermit", petit-fils d'un autre Kermit qui a écrit après la grande guerre (la première guerre mondiale). La recherche "kermit great war" pointe vers Kermit Roosevelt (fils de l'ancien président Théodore), qui a servi durant la guerre, et qui a bien écrit à son propos ensuite :

<img src="/images/2023-HEXA/2023-01-31 17_25_41-Kermit Roosevelt - Wikipedia —.png" alt="2023-01-31 17_25_41-Kermit Roosevelt - Wikipedia — Mozilla Firefox.png" width="436" height="119" class="jop-noMdConv">

Autre point de concordance, concernant le Kermit "*third of his name*", il a un fils Kermit Jr. et un petit-fils Kermit Roosevelt III.

Ensuite le second roman ... est-ce qu'il s'agit du second du grand-père ou du petit-fils ? Rien ne ressort coté romans concernant le grand-père. À l'opposé, le petit-fils a publié plusieurs livres dont "Allegiance", sa seconde "novel" :

<img src="/images/2023-HEXA/2023-01-31 17_30_58-Kermit Roosevelt III - Wikiped.png" alt="2023-01-31 17_30_58-Kermit Roosevelt III - Wikipedia — Mozilla Firefox.png" width="746" height="248" class="jop-noMdConv">

La partie "*the actor he will see to take the role of the main character in a movie theater*" me questionne, s'agit-il de l'auteur du roman qui souhaiterait voir son héros (le personne principal du roman est Caswell “*Cash*” Harrison) incarné par l'acteur ou est-ce une partie de l'ouvrage ?

Concernant la second hypothèse, la [page Google Books](https://www.google.fr/books/edition/Allegiance/lbd0BgAAQBAJ?hl=fr&gbpv=0) n'apporte rien, la recherche sur le terme "acteur"  dans les pages du livre disponibles non plus. La première hypothèse s'avère la bonne, une recherche ""kermit roosevelt" allegiance actor cash" mène à [un article de Harvardwood](https://www.harvardwood.org/mp201510 "Harvardwood ") et l'acteur recherché :

<img src="/images/2023-HEXA/2023-01-31 10_14_17-October 2015 _ Kermit Roosevel.png" class="jop-noMdConv">

### He is back 2 

300 points - *You get the answer to the question your colleague was asking, and you reach him to notice on his desk a paper noted "my personal recipe" with chemical compounds. You are able to discreetly eye catch a part of the recipe and once out of your colleague office, you write it down :three cyclohexaneone cyclopentaneYou are intrigued by this recipe and wonder if you can found the scientific name of this recipe...*

**NON VALIDÉ**

Après avoir cherché les formules chimiques des deux éléments (C₆H₁₂ / C₅H₁₀), il paraissait compliqué de les manipuler (la chimie ne m'a jamais parlé !). <br>
J'ai alors tenté simplement la recherche "three cyclohexanes and one cyclopentane". Il est assez clair qu'il s'agit d'une recette pour fabriquer des stéroides au vu des résultats. Par exemple sur le [premier résultat,](https://www.toppr.com/ask/question/steroid-nucleus-contains/ "steroid nucleus") on parle de "steroid nucleus". Ces éléments ne passent pas en flag. <br>

Ainsi je dois me concentrer à chercher un nom plus scientifique. À partir de la [fiche Wikipedia de Steroid,](https://en.wikipedia.org/wiki/Steroid) on retrouve les termes "Gonane" et "Sterane", là non plus pas de réussite coté flag. Arrivant à la deadline et ayant déjà trop insisté sur les tentatives, j'ai pensé faire fausse route.

Erreur un peu frustrante ! En réalité, une fois le CTF terminé j'ai pu découvrir la réponse correcte (et son nom scientifique pour sûr !), celle-ci était à porté d'œil sur la [page Wikipedia de "Steroid"](https://en.wikipedia.org/wiki/Steroid) :

<img src="/images/2023-HEXA/2023-01-31 10_05_54-Steroid - Wikipedia — Mozilla .png" class="jop-noMdConv">

* * *

## The Lawyer

### The law firm

*The Swiss law firm representing Lucilhe is known as Nelexat. We would like to check that this law firm has all the authorizations to work as a lawyer in France. Could you find their website?*

Avec le nom de l'entreprise et le pays, l'association logique fonctionne, le site de l'entreprise est [http://nelexat.ch/](http://nelexat.ch/ "Escrocs "). Élément à noter, le site apparaît comme non sécurisé.

### Alias

*Thanks to this social media account, you learned that this lawyer seems to give some advices about money. Maybe you can find another account on some trading platform...*

Il apparaît après le challenge [The lawyer](#the-lawyer-1). En parcourant les activités [LinkedIn de Lian,](https://www.linkedin.com/in/lian-nussbaumer-92b89b253/recent-activity/shares/ "LinkedInLian") on peut vérifier sa passion pour l'argent et les montres, mais surtout trouver l'annonce d'une conférence à venir. Sur le visuel, on y remarque ce qui ressemble à des pseudonymes (mention spéciale pour "GiantIncomesForYou"). Nelexlian est l'alias de Lian Nussbaumer :

<img src="/images/2023-HEXA/2023-01-29 12_02_19-LinkedIn.png" alt="2023-01-29 12_02_19-LinkedIn.png" width="661" height="236" class="jop-noMdConv">

Maintenant, il s'agit de trouver la plateforme de trading. Je pense directement à Robinhood ou bien eToro que je connais pour son aspect "réseau social". Une recherche sur eToro permet de [retrouver son profil](https://www.etoro.com/people/nelexlian "Nexlexlian ") et le flag demandé :

<img src="/images/2023-HEXA/2023-01-31 15_50_02-NelexLian @NelexLian – eToro —.png" alt="2023-01-31 15_50_02-NelexLian @NelexLian – eToro — Mozilla Firefox.png" width="712" height="232" class="jop-noMdConv">

### Good times

*We are progressing in the hunt thanks to your information. Keep going! The invitation that you have just found mentions a place for the meeting, can you help us to identify this place?*

Suite de [Herbaceous](#herbaceous), dans son agenda, Mastermind convie deux de ses associés à un rendez-vous à Zurich :

<img src="/images/2023-HEXA/2023-01-31 15_32_54-Google Agenda - Semaine du 12 .png" alt="2023-01-31 15_32_54-Google Agenda - Semaine du 12 décembre 2022.png" width="319" height="517" class="jop-noMdConv">

Je me base sur ces éléments pour avoir des informations sur le lieu de la rencontre. La recherche des mails ne donne aucun résultat sur https://epieos.com/. Il faudra rechercher le seul identifiant "mincah_mm" sur https://whatsmyname.app/ pour avoir un résultat :

*<img src="/images/2023-HEXA/2023-01-31 13_45_54-WhatsMyName Web.png" alt="2023-01-31 13_45_54-WhatsMyName Web.png" width="463" height="130" class="jop-noMdConv">*

Le lien mène au profil Tripadvisor de l'associée qui évoque son passage dans le restaurant recherché pour le meeting avec son équipe :

<img src="/images/2023-HEXA/2023-01-31 13_42_33-Minca H (@mincah_mm) - Profile.png" alt="2023-01-31 13_42_33-Minca H (@mincah_mm) - Profile - Tripadvisor.png" width="417" height="280" class="jop-noMdConv">

### The lawyer

*Lucilhe's lawyer usually don't take this kind of case. Nelexat is specialized in financial advice and is representing Lucilhe on a misdemeanor case in France. This situation is unusual, even if the law firm has all the authorizations. Could you find the last city where the owner of Nelexat studied?*

Cette étape primordiale (elle conditionne aussi les suivants de la timeline "The Lawyer") en début de challenge a été fastidieuse. 

Avant de pouvoir trouver sa dernière ville d'études, il va falloir trouver son identité  Après un premier tour du site, aucun nom ne ressort dans les pages ou coté [whois](https://whois.domaintools.com/ "Who Is"). Une recherche google sur le nom de domaine ne donne pas plus d'infos.

D'office, l'intitulé laisse penser à un profil LinkedIn, premier réseau social professionnel. Une occurrence ressort mais le profil et le nom est inaccessible par cette entrée :

<img src="/images/2023-HEXA/2023-01-31 16_59_31-_nelexat_ _ Recherche _ Linked.png" alt="2023-01-31 16_59_31-nelexat _ Recherche _ LinkedIn — Mozilla Firefox.png" width="403" height="119" class="jop-noMdConv">

Après avoir laissé passer la nuit, et m'être replié sur d'autres challenges, j'en suis revenu à l'[archive du site au 5 janvier](https://web.archive.org/web/20230105145658/http://www.nelexat.ch/) déjà consultée mais sans y avoir assez passé de temps / avoir été assez attentif. 

Dans cette archive, j'avais bien remarqué d'abord quelques différences comme le "Contact us" en bas de page, le "made by Olga Vokolska" mais pas le "Lian  Nussbaumer" en plein milieu de la page "Terms et conditions" :

<img src="/images/2023-HEXA/2023-01-31 17_19_19-Terms and conditions – Nelexat.png" alt="2023-01-31 17_19_19-Terms and conditions – Nelexat — Mozilla Firefox.png" width="506" height="222" class="jop-noMdConv">

À partir de là, une recherche sur LinkedIn avec le nom et le prénom permet de retrouver le [profil](https://www.linkedin.com/in/lian-nussbaumer-92b89b253/) et la dernière ville d'études :

<img src="/images/2023-HEXA/2023-01-31 17_20_52-Lian Nussbaumer _ LinkedIn.png" class="jop-noMdConv">

### Trustwhorthy

*Nelexat's website apparently has no contact information. Maybe an email address has been hidden on that website. Could you help us to find this email?*

Rien dans les contenus du site, rien non plus sur les [contenus du site de l'archive du 5 janvier.](https://web.archive.org/web/20230000000000*/http://nelexat.ch/ "wayback") Je tente alors d'utiliser [Dirb](https://www.kali.org/tools/dirb/ "Dirb") pour trouver d'autres répertoires, sans résultat probant pour ce challenge.

En y revenant plus tard, j'ai finalement pensé à la vérification du certificat et suis parvenu à l'adresse mail : mastermind_mastermind@proton.me.

<img src="/images/2023-HEXA/2023-01-31 16_07_55-Nelexat – Why pay the state wh.png" class="jop-noMdConv">

### Herbaceous

*You found an email, that's great. Could you use this email to find interesting information?*

En passant le mail à la [recherche Epieos,](https://epieos.com/ "epieos") on parvient à son [calendrier Google](https://calendar.google.com/calendar/u/0/embed?src=mastermind_mastermind@proton.me&pli=1 "Mastermind agenda") avec une invitation et un lien vers un site .onion. 

<img src="/images/2023-HEXA/2023-01-31 15_33_12-mastermind_mastermind@proton.m.png" class="jop-noMdConv">

En utilisant Tor, on parvient au site indiqué. On y découvre les services plus secrets de Mastermind avec son adresse blockchain : 0x64D0D945AE5a384c18A3876064816b7E141980E7. Autre élément, qui servira plus tard au moment de [Final Countdown](#final-countdown) un lien vers un fichier .kmz avec différentes zones géographiques situées en Malaisie.

<img src="/images/2023-HEXA/2023-01-29 21_36_18-Mastermind — Tor Browser.png" alt="2023-01-29 21_36_18-Mastermind — Tor Browser.png" width="730" height="387" class="jop-noMdConv">

Le flag demandé ici se trouve en affichant le code source de la page.

<img src="/images/2023-HEXA/2023-02-01 22_01_39-Mastermind — Tor Browser.png" class="jop-noMdConv">

### Decentralized

*Oh my god, you found something huge, this MasterMind team seems to sell services using cryptocurrency, maybe you can go further in your investigation with this piece of information and find something useful, like a mission name related to one of their client.*

Depuis blockchain.com, nous pouvons tracer les dernières transactions de Mastermind (0x64D0D945AE5a384c18A3876064816b7E141980E7). On repère dans la première transaction fin décembre une partie "data" plutôt inhabituelle :

<img src="/images/2023-HEXA/2023-02-01 18_55_25-Transaction_ 0x0f81151afd64b7b.png" alt="2023-02-01 18_55_25-Transaction_ 0x0f81151afd64b7b3fdda7dbd898d9f68840c5e58c3dc208b6504c798d6c9753a .png" width="662" height="490" class="jop-noMdConv">

En passant à [Cyberchef](https://gchq.github.io/CyberChef/ "Cyberchef") la data, on décode "From Hex" :

<img src="/images/2023-HEXA/2023-01-29 17_35_40-Magic - CyberChef — Mozilla Fi.png" class="jop-noMdConv">

Le nom de la mission est "Bruised Rogue". On y trouve également le mail de Tsuzune Yokoyama [précédemment croisé](#tell-me-owl-your-secrets) (je n'en aurais pas utilité par la suite).

Il est possible de se renseigner sur ce dossier depuis la [doc fastAPI](#experts) :

<img src="/images/2023-HEXA/2023-02-01 18_33_23-FastAPI - Swagger UI.png" class="jop-noMdConv">


### Experts

*It seems that Nelexat has a lot of expertise in taxes and gives advices about diverse topics. Maybe you could find something useful about the clients Nelexat is defending.*

On remarque sur la page de nelexat.ch dans la partie "Our advices" un lien vers un framework "fastapi hosted on 217.182.69.14:8000". Après renseignement sur le fonctionnement de fastAPI, pour accèder à la documentation, il sera nécessaire de rajouter "/docs" : http://217.182.69.14:8000/docs

<img src="/images/2023-HEXA/2023-02-05 21_19_48-Our advices – Nelexat — Mozilla Firefox.png" class="jop-noMdConv"> 

La recherche du le nom de la cliente "Dumarquais" permet d'obtenir la description du dossier et le flag :

<img src="/images/2023-HEXA/2023-02-01 18_33_43-FastAPI - Swagger UI.png" class="jop-noMdConv">

### Kanagawa

*They may use their cryptocurrency address for something else, try to find something...*

Que peut-on faire d'autres avec des cryptomonnaies ? Acquérir des NFTs ! (merci à un challenge marquant rencontré sur [OZINT](https://ozint.eu/ "Ozint")).

La marketplace principale est https://opensea.io/. En recherchant l'adresse blockchain de Mastermind, on débouche sur le profil de "Mind_master" avec le visuel rencontré sur sa page .onion :

<img src="/images/2023-HEXA/2023-02-03 12_59_43-Window.png" class="jop-noMdConv">

Le flag est est sur la [page du NFT](https://opensea.io/assets/ethereum/0x495f947276749ce646f68ac8c248420045cb7b5e/45600288605355569432684790323838389341572314161561028917962474406085593661441) :

<img src="/images/2023-HEXA/2023-02-03 13_01_30-Window.png" alt="2023-02-03 13_01_30-Window.png" width="316" height="406" class="jop-noMdConv">

* * *

## The Developer

### Programming

*This company is definitely suspicious. Someone must have developed their website and we would like to see if this person has any connection with our case. This person must have an account for his IT projects. Can you find it?*

Le [passage à Dirb](#trustwhorthy) permet de retrouver le dossier /.git et le dépôt du développeur. Son contact est dans le fichier config :

<img src="/images/2023-HEXA/2023-02-01 18_10_19-HEXA.png" class="jop-noMdConv">

La recherche sur https://whatsmyname.app/ de "ovokolska" amène à [son profil GitHub](https://github.com/ovokolska).

### Listen to your heart

*Well done, now that you have found an account, let's try to find intimate information about this developer.*

Sur le [profil GitHub](https://github.com/ovokolska "Profil GitHub") en question, on trouve une description "littleSparr0w".

<img src="/images/2023-HEXA/2023-02-01 18_20_19-OVokolska (OVokolska) — Mozill.png" alt="2023-02-01 18_20_19-OVokolska (OVokolska) — Mozilla Firefox.png" width="247" height="209" class="jop-noMdConv">

En recherchant la description sur https://whatsmyname.app/, on retrouve beaucoup de profils sous cet intitulé. On recherche des informations intimes sur la personne, pour ce type d'infos je me tourne d'abord vers les réseaux sociaux. J'imagine un profil type Twitter ou Reddit. <br>Ces profils existent bien mais il ne s'agit pas de notre cible. Après avoir parcouru plusieurs profils avec ce pseudonyme, la solution vient du coté de Mastodon. On retrouve des bouts de vie sur [son profil](https://cyberplace.social/@littlesparr0w "Profil Mastodon") et surtout le flag recherché :

<img src="/images/2023-HEXA/2023-02-01 18_27_09-littlesparr0w (@littlesparr0w@.png" alt="2023-02-01 18_27_09-littlesparr0w (@littlesparr0w@cyberplace.social) - Cyberplace — Mozilla Firefox.png" width="382" height="188" class="jop-noMdConv">

***
## Bilan 

![](/images/2023-HEXA/1.png)
![](/images/2023-HEXA/2.png)
