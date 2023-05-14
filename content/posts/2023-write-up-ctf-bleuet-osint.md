---
title: Retour sur la deuxième édition du CTF Bleuet 2023 de l'AEGE
date: 2023-05-14
series  : "Write-ups"
tags: ["Bleuet","CTF"]

---
L'[AEGE](https://www.aege.fr) a proposé la seconde édition de son **[CTF "Bleuet" historique et mémoriel](https://bleuet.aege.fr/)**. Organisé par le [Club OSINT & Veille de l'AEGE,](https://www.aege.fr/groupe/club-osint-veille-18) il s'est déroulé entièrement en ligne du 5 au 14 mai 2023. Les participants ont du résoudre des énigmes contenant des informations sur des personnes ou des faits durant la seconde guerre mondiale en se basant sur des recherches en sources ouvertes (ROSO / OSINT).

Derrière l'aspect challenges OSINT, ce fût l'occasion de (re)découvrir un pan de l'histoire de manière très plaisante (hormis quelques migraines :)). Je pense par exemple à l'[histoire des Rochambelles](https://www.marinettes-et-rochambelles.com/) ou les [stratégies de la division Leclerc](https://www.2edb-leclerc.fr/liberation-de-paris-3/) lors de la libération de Paris.

Merci aux organisateurs, vous les retrouvez via le [club OSINT & Veille de l'AEGE](https://www.aege.fr/groupe/club-osint-veille-18) et la [Newsletter, le MAG'OSINT.](https://www.aege.fr/news/magosint-8335)

Enfin, il est possible tout au long de l'année de **soutenir l'Office national des combattants et des victimes de guerre** directement sur : **[www.onac-vg.fr/soutenir-le-bleuet-de-france.](https://www.onac-vg.fr/soutenir-le-bleuet-de-france)**

***

## En avant !

### Une promesse tenue - 25

*Quel bâtiment clôt une célèbre formule prononcée à l’issue d’une victoire décisive de la 2ème division blindée ?*

Comme point d'entrée, je me rends sur la [page Wikipédia de la 2ème division blindée](https://fr.wikipedia.org/wiki/2e_division_blind%C3%A9e_%28France%29). Cela sera suffisant puisqu'on retrouve une partie de la formule prononcée suite à la première victoire de Koufra :

<img src="/images/2023-BLEUET/2023-05-14 16_10_30-2e division blindée (France) —.png" alt="date" width="583"  class="jop-noMdConv">

-\> Flag : BLEUET{cathédrale}

### L'homme providentiel - 25

<img src="/images/2023-BLEUET/60e7a168ba38db85734f081a5933d9aa" alt="newspaper.png" width="283" height="429" class="jop-noMdConv">

1.  *Dans quel journal cet article relatif au général Leclerc a été publié ?*
2.  *Quelle est sa date de parution ?*

En regardant l'image dans le détail, on remarque un article de presse en langue anglaise. Autre élément, à droite de l'image on trouve une publicité avec le "£" de la livre sterling. On peut en déduire qu'il s'agit d'un article d'un journal du Royaume-Uni. Une recherche sur "british newspaper archive" permet d'arriver sur https://www.britishnewspaperarchive.co.uk/. Ce site donne accès aux archives numérisées des journaux britanniques et irlandais.

La recherche sur un élément du texte de l'article, par exemple "Leclerc the man who relieved Paris" permet d'obtenir la solution au challenge : l'article a été publié dans le Hull Daily Mail le vendredi 26 mai 1972.

<img src="/images/2023-BLEUET/2023-05-12 14_58_30-Results for _leclerc the man w.png" alt="2023-05-12 14_58_30-Results for 'leclerc the man who relieved paris' _ British Newspaper Archive — M.png" width="827" height="337" class="jop-noMdConv">

-\> Flag : BLEUET{hull\_daily\_mail\_26\_05_1972}

### Libérez Malakoff - 50

*Lors de la Libération de Malakoff, des hommes de la 2ème division blindée ont dû percer un passage chez une dame pour faire passer des chars.*

*Cette dernière s'en est allée se plaindre auprès de la mairie alors que la ville était sous occupation.*

*Sur le rapport adressé au Maire et écrit par le garde champêtre, on peut lire « Dégâts causés par char de combat ».*

*Quel est le numéro du rapport ?*

*Attention, cinq essais maximum !*

Je cherche d'abord de potentiels archives municipales sans succès. En y revenant plus tard, je trouve l'évocation du témoignage d'André Espi, ancien de la 2ème DB sur le [site Malakoff Patrimoine.](https://malakoffpatrimoine.fr/index-fr.php?page=web-tv&id_article=1281)

La vidéo n'est pas lisible directement mais retrouvable via YouTube ou intégré au [forum 2DB de passionnés de l'unité](https://2db.forumactif.com/t3061-malakoff-hauts-de-seine) :

<img src="/images/2023-BLEUET/2023-05-10 22_48_03-Malakoff Hauts-de-Seine — Mozi.png" alt="2023-05-10 22_48_03-Malakoff Hauts-de-Seine — Mozilla Firefox.png" width="550" height="406" class="jop-noMdConv">

André Espi y évoque cet épisode et le scan de la plainte en question portant le numéro 78. 

-\> Flag : BLEUET{78}

### Par le sang versé - 50

*Un témoignage raconte : « Mon capitaine a libéré Paris, mais pas moi. Avec un camarade, nous avons été fauchés par un 88 allemand. Par notre sacrifice, nous avons ouvert la voie de Paris. » « J’étais jeune, très jeune, je sortais de l’enfance. »*

1.  *Quel est le nom de ce soldat ?*
2.  *Dans quel lycée a-t-il étudié ?*

J'ai commencé par écumer les cas pouvant correspondre à partir de la page sur [les coûts humains dans la "bataille de Paris" du site de Gilles Primout](https://liberation-de-paris.gilles-primout.fr/sur-les-traces-de-la-2eme-division-blindee). D'abord sur une fausse piste de Jacques Boutard (tué lui aussi avec un camarade par des canons de 88), tout concordait pour le [soldat "De La Roche"](https://www.memorialgenweb.org/memorial3/html/fr/complementter.php?id=6497724) : 

<img src="/images/2023-BLEUET/2023-05-11 17_56_05-.png" alt="2023-05-11 17_56_05-.png" width="824" height="411" class="jop-noMdConv">

Pour son lycée, en creusant via recherches web on arrive sur [ce site](http://www.lyceefr.org/aaegd/gouraud/livredor/de_la_roche_geoffroy.htm) racontant l'histoire du jeune homme à la manière de la consigne. 

Pour l'anecdote, dans mes pérégrinations je me suis tourné à un moment vers chatGPT, et bien déçu : 

<img src="/images/2023-BLEUET/2023-05-11 00_04_33-Mitterrand_s Sacrifice — Mozil.png" alt="2023-05-11 00_04_33-Mitterrand's Sacrifice — Mozilla Firefox.png" width="688" height="317" class="jop-noMdConv">

-\> Flag : BLEUET{de\_la\_roche_gouraud}

### Par le sang versé, partie 2 - 50

*Les Allemands ont tiré neuf fois sur un char aux alentours de Paris avant qu’il ne brûle avec, à son bord, un maréchal des logis.*

*Les militaires aiment les devises hautes en couleurs, ceux de la 2 particulièrement.*

*Retrouver le nom du char ainsi que la devise qui lui était associée.*

Avec [la même source](https://liberation-de-paris.gilles-primout.fr/sur-les-traces-de-la-2eme-division-blindee) que pour "Par le sang versé, partie 1", nous retrouvons ce cas : 

<img src="/images/2023-BLEUET/2023-05-14 23_17_32-Sur les traces de la 2ème DB (.png" alt="sang versé" width="597"  class="jop-noMdConv">

Sa devise est trouvable ensuite par exemple via le [site des musées de la ville de Paris](https://www.parismuseescollections.paris.fr/fr/musee-jean-moulin/oeuvres/fanion-du-char-sherman-barfleur-2eme-peloton-2eme-escadron-12eme-regiment) avec la devise "Fonce et bute" : 

<img src="/images/2023-BLEUET/2023-05-11 17_59_56-Fanion du char Sherman _Barfle.png" alt="2023-05-11 17_59_56-Fanion du char Sherman Barfleur - 2ème peloton, 2ème escadron, 12ème Régiment .png" width="597" height="423" class="jop-noMdConv">

-\> BLEUET{barfleur\_fonce\_et_bute}

### Le square carré - 75

*À quelques mètres de cet immeuble se trouve un square. La date de l'évènement clé est le code pour déchiffrer l’image brouillée en pièce jointe.*

<img src="/images/2023-BLEUET/Square.png" alt="Square.png" class="jop-noMdConv">
<img src="/images/2023-BLEUET/image_online.png" alt="image_online.png" class="jop-noMdConv">

1.  *Qui se trouve sur la photograhie ?*
2.  *Quel est le numéro d'immatriculation du moyen de transport lui ayant permis de rejoindre le Général de Gaulle par la Manche ?*

Pour trouver le code, on repère sur la première image la devanture "Peugeot Scooters" et le panneau "Département des Hauts ...". Il ne peut s'agir que des Hauts-de-Seine puisque les Hauts-de-France sont une région. La recherche combinée des éléments permet de retrouver une partie de magasin à Montrouge qui ressemble beaucoup :

<img src="/images/2023-BLEUET/2023-05-11 18_22_08-_peugeot scooters_ haut de sei.png" alt="2023-05-11 18_22_08-peugeot scooters haut de seine – Recherche&nbsp;Google — Mozilla Firefox.png" width="558" height="313" class="jop-noMdConv">

Cela est se confirme via Streetview, on trouve à proximité le Square du Serment-de-Koufra. La date de l'évènement est donc le 2 mars 1941.

<img src="/images/2023-BLEUET/2023-05-11 18_22_46-16 Av. de la République - Goog.png" alt="2023-05-11 18_22_46-16 Av. de la République - Google&nbsp;Maps.png" width="527" height="338" class="jop-noMdConv">

Maintenant pour déchiffrer l'image, le .png chiffré est nommé "image_online". Il s'agit de différents services d'édition d'images en ligne, et notamment le [chiffrage / déchiffrage avec un mot de passe.](https://decrypt.imageonline.co/index-fr.php) 

En ajoutant notre fichier et le mot de passe (la date, après quelques essais pour trouver le bon format), le personnage mystère n'est autre que Philippe Leclerc de Hauteclocque.

*<img src="/images/2023-BLEUET/2023-05-11 18_29_34-Decrypt image online - Decrypt.png" alt="2023-05-11 18_29_34-Decrypt image online - Decrypt _ Decipher an image using secret password - free .png" width="595" height="362" class="jop-noMdConv">*

Pour rejoindre le Général de Gaulle, il va monter à bord du SS Hilary à en croire [sa fiche Wikipedia](https://fr.wikipedia.org/wiki/Philippe_Leclerc_de_Hauteclocque) :

<img src="/images/2023-BLEUET/2023-05-14 21_42_49-Philippe Leclerc de Hauteclocq.png" alt="2023-05-14 21_42_49-Philippe Leclerc de Hauteclocque — Wikipédia — Mozilla Firefox.png" width="873" height="99" class="jop-noMdConv">

Le numéro d'immatriculation 162350 est à retrouver sur la [fiche Wikipedia du "SS Hilary"](https://en.wikipedia.org/wiki/HMS_Hilary_%281940%29) :

<img src="/images/2023-BLEUET/2023-05-11 18_37_10-HMS Hilary (1940) - Wikipedia .png" alt="2023-05-11 18_37_10-HMS Hilary (1940) - Wikipedia — Mozilla Firefox.png" width="897" height="150" class="jop-noMdConv">

***
## Mémoire

### Asso - 25

*Quelle est la date de création de la première association relative aux anciens de la Division Leclerc ?*

L'information est disponible sur le [site de l'Association de la Maison des Anciens de la 2ème D.B :](https://www.2edb-leclerc.fr/lassociation-des-anciens-de-la-2eme-db-2/)*"Ses statuts sont déposés à Paris le 21 août 1945.".*

-\> BLEUET{21\_08\_1945}

### Vraie date ? - 25

*Rosette Peschaud, ambulancière militaire française dans le Groupe Rochambeau, avance quant à elle une autre date pour la création de l'association. Laquelle ?*

 "*Avance quant à elle*" : on est forcément sur un témoignage dans une interview ou bien dans un ouvrage. Après avoir écumé les moteurs de recherches et visionné plusieurs vidéos témoignages de Madame Peschaud, j'étais fort dépourvu. La solution viendra plus tard via Google Books en retrouvant son l'ouvrage [*Soldats de Leclerc : récits et anecdotes (1940-1946)*](https://www.google.fr/books/edition/Soldats_de_Leclerc_r%C3%A9cits_et_anecdotes/UHtYDwAAQBAJ?hl=fr&gbpv=1&dq=Soldats+de+Leclerc+:+r%C3%A9cits+et+anecdotes+%281940-1946%29&printsec=frontcover) (chapitre "Les Anciens de la 2è DB") : 

*<img src="/images/2023-BLEUET/2023-05-07 13_25_19-Soldats de Leclerc _ récits et.png" alt="2023-05-07 13_25_19-Soldats de Leclerc _ récits et anecdotes (1940-1946) - Rosette Peschaud - Google.png" width="702" height="360" class="jop-noMdConv">*

-\> BLEUET{22\_06\_1945}

### Ad vitam - 25

*Preuve que le devoir de mémoire subsiste, deux anciens membres de la deuxième DB, nés en 1908 et 1909, ont été récemment honorés. Comment s'appellent-ils ? (Indiquez simplement les noms de famille, en commençant par le plus ancien).*

Les dates laissent imaginer que les deux anciens membres sont décédés. "Récemment honorés" doit alors être à titre posthume, il semble logique alors de regarder du coté des cérémonies / commémorations.

Le site de l'association des Anciens de la 2ème DB [dispose de cet agenda.](https://www.2edb-leclerc.fr/agenda-2023/) En remontant jusqu'à mars 2023, on remarque l'"inauguration de stèles CREPIN & GUILLEBON" :

*<img src="/images/2023-BLEUET/2023-05-09 22_27_11-Google-agenda _ 2e DB - Généra.png" alt="2023-05-09 22_27_11-Google-agenda _ 2e DB - Général LECLERC - 2ème Division Blindée — Mozilla Firefo.png" width="748" height="395" class="jop-noMdConv">*

Cela concorde bien avec les années de naissances retrouvées via les pages Wikipedia des concernés :

<img src="/images/2023-BLEUET/2023-05-09 22_27_49-Jean CRÉPIN - Recherche Google.png" alt="crepin"  class="jop-noMdConv">

*<img src="/images/2023-BLEUET/2023-05-09 22_28_11-Jacques de Guillebon — Wikipéd.png" alt="2023-05-09 22_28_11-Jacques de Guillebon — Wikipédia — Mozilla Firefox.png" width="763" height="251" class="jop-noMdConv">*

-\> Flag : BLEUET{crepin\_de\_guillebon}

### Le don - 50

*Outre les écrits, le souvenir se transmet aussi grâce aux dons. La prénommée Paulette en a justement effectué 9 en 2004. Mais comment s'appelle cette généreuse donatrice ?*

J'étais parti dans l'idée de dons financiers, ainsi j'ai recherché les remerciements par exemple dans la [revue "Caravane"](https://www.2edb-leclerc.fr/publications/caravane/) de la division Leclerc autour de 2004. Au final, en recentrant simplement sur une recherche "paulette dons 2004 "libération de paris"", on arrive sur le [site des musées de la Ville de paris](https://www.parismuseescollections.paris.fr/) qui répertorie les collections en précisant le nom du donateur / testateur / vendeur et la date d'acquisition. En regardant dans le détail, Paulette VALY aura donné [9 œuvres](https://www.parismuseescollections.paris.fr/fr/recherche?keywords=paulette%20valy), toutes en 2004.

-\> Flag : BLEUET{valy}

### La carte - 50

*Le 26 avril dernier, une carte postale présentant des rochambelles a été publiée.*

*Combien de ces infirmières sont présentes sur la carte ?*

Dernier challenge, une seule tentative, pas le droit à l'erreur. Je commence à fouiller du coté des sites / pages dédiés aux Rochambelles puis aux réseaux sociaux liés sans succès (beaucoup d'éléments intéressants néanmoins sur [https://www.facebook.com/lesfillesdeladb/?locale=fr_FR)](https://www.facebook.com/lesfillesdeladb/).

La recherche Google avec Rochambelles et la date du 26 avril ne donne rien non plus. Ensuite, pas mieux au niveau des sites et bourses de cartes postales.

Au final, l'entrée "cartes postales" était la bonne mais via Facebook et le groupe "[Cartes postales et photos anciennes](https://www.facebook.com/photo.php?fbid=963918358230071&set=pb.100038357474371.-2207520000.&type=3)". On dénombre 9 Rochambelles au premier plan de cette publication du 26 avril :

<img src="/images/2023-BLEUET/2023-05-12 14_39_33-Facebook — Mozilla Firefox.png" alt="2023-05-12 14_39_33-Facebook — Mozilla Firefox.png" width="961" height="396" class="jop-noMdConv">

-\> Flag : BLEUET{9}

***
## Vestige

### Archéologie - 25

*Un document de l’époque appartenant à une unité de la 2è division blindée a été retrouvé lors de fouilles.*

<img src="/images/2023-BLEUET/3c12771b06ed954b5ab5686509e4ea33" alt="Image4.jpg" width="165" height="124" class="jop-noMdConv">

*À quel lieu fait-il référence ?*

J'ai reconnu rapidement une écriture arabe en première ligne, mais le passage à Google Lens / traduction n'a rien donné de pertinent. Dans un second temps, en faisant des recherches sur les caractères de la second ligne, je suis tombé sur l'[alphabet Berbère](https://fr.wikipedia.org/wiki/Tifinagh) qui colle avec les lettres données. Le lieu est [Témara](https://fr.wikipedia.org/wiki/T%C3%A9mara) (ⵜⵎⴰⵔⴰ en berbère) (cela coincide aussi avec l'histoire de la 2eme DB).

<img src="/images/2023-BLEUET/2023-05-05 21_34_46-TMARA - Recherche Google — Moz.png" alt="2023-05-05 21_34_46-TMARA - Recherche Google — Mozilla Firefox.png" width="430" height="188" class="jop-noMdConv">

-\> Flag : BLEUET{témara}

### Le Sherman - 25

*Ce char Sherman a été capturé au cours d'une bataille.*

![Image5.jpg](/images/2023-BLEUET/a35d709c8f1e3960ca077c5ef6d21752)

*Quel est le matricule de ce char et le nom de son chef ?*

On distingue un 5, et potentiellement un 3 juste devant. Cela se confirme via recherche Google inversée puis sur le [site "Chars Francais"](https://www.chars-francais.net/2015/index.php/16-classement-individuel/sherman/826-corse-12rca) où l'on retrouve l'image donnée et le numéro de matricule "420-644" : 

<img src="/images/2023-BLEUET/2023-05-05 21_46_27-CORSE 12RCA — Mozilla Firefox.png" alt="2023-05-05 21_46_27-CORSE 12RCA — Mozilla Firefox.png" width="561" height="518" class="jop-noMdConv">

-\> Flag : BLEUET{420-644_corse}

### Sur les traces de la 2 - 75

<img src="/images/2023-BLEUET/7bc9b35c8a6e9af9435193a770a1e9fb" alt="sur_les_traces_de_la_2.png" width="623"  class="jop-noMdConv">

1.  *À quelle ville fait référence le monument présent à gauche de ce cliché ?*
    
2.  *Que cache-t-il ?*
    

*Petit indice : le "il" de "que cache-t-il" se rapporte au monument ou à autre chose ... ?*

La première partie est trouvable via recherche d'images inversée, il s'agit du monument de la 2ème DB de Fyé, la ville nommée est Alençon : <img src="/images/2023-BLEUET/2023-05-05 22_01_31-(1) Facebook — Mozilla Firefox.png" alt="2023-05-05 22_01_31-(1) Facebook — Mozilla Firefox.png" width="758" class="jop-noMdConv">

La seconde partie n'était pas si simple.

Après avoir tourné en rond et cherché différentes pistes en stéganographie, j'ai fini par repérer l'astuce (juste après avoir désactivé le filtre f.lux en fait :)). On distingue plusieurs marques un peu jaune (ici les éléments marqués) : -. . .- ..-.. -... . Cela ressemble à des éléments de code morse. 

<img src="/images/2023-BLEUET/Inkedsur_les_traces_de_la_2_LI.jpg" alt="Inkedsur_les_traces_de_la_2_LI.jpg" width="872" class="jop-noMdConv">

En recopiant ces éléments, par exemple sur [dcode.fr,](/C:/Program%20Files/Joplin/resources/app.asar/dcode.fr) on arrive au flag soit bleuet à l'envers :

<img src="/images/2023-BLEUET/2023-05-10 18_34_03-Code Morse - Alphabet - Traduc.png" alt="morse" width="572" class="jop-noMdConv">

-\> Flag : BLEUET{alençon_teuelb}

***
## GEOINT

### Des chars, encore des chars ! - 25

*Le char M4A2 est actuellement conservé au musée des blindées de Saumur, mais un autre char Sherman « Corse » est exposé ailleurs.*

1.  *Dans quelle ville est-il exposé ?*
2.  *Quel est numéro inscrit à l’avant et à l'arrière de ce char ?*

À partir de recherche web, on retrouve l'autre char Sherman "Corse" à Madonne-et-Lamerey : 

*<img src="/images/2023-BLEUET/2023-05-07 13_48_15-Char Sherman _Corse_, commémor.png" alt="2023-05-07 13_48_15-Char Sherman Corse, commémorant la bataille de Dompaire — Mozilla Firefox.png" width="677" height="370" class="jop-noMdConv">*

Des photos de l'arrière du char postées par des visiteurs du Monument Leclerc de Dompaire sont trouvables [via les contributions Google :](https://www.google.com/search?q=monument+de+Dompaire&oq=monument+de+Dompaire&aqs=chrome..69i57.141j0j7&sourceid=chrome&ie=UTF-8#lrd=0x47931314c56adc41:0x2b1f7e6dc72d20e6,1,,,,)

*<img src="/images/2023-BLEUET/2023-05-07 13_51_46-Le Monument Leclerc de Dompair.png" alt="2023-05-07 13_51_46-Le Monument Leclerc de Dompaire - Google&nbsp;Maps — Mozilla Firefox.png" width="687" height="376" class="jop-noMdConv">*

-\> Flag : BLEUET{madonne\_et\_lamerey_420050}

### 360 degrés - 25

*Maintenant que les coordonnées GPS sont en votre possession, sur quelle façade se trouve la plaque commémorative de cet évènement ? (N : Nord / E : Est / O : Ouest / S : Sud)*

*Attention, vous n'avez qu'un seul essai !*

Via Google Streetview, on peut observer la plaque de manière lointaine, elle se situe sur la façade Nord.
<img src="/images/2023-BLEUET/2023-05-14 22_48_18-2e division blindée (France) —.png" alt="DB" width="187"  class="jop-noMdConv">
-> Flag : BLEUET{N}

### Vous avez dit Gre... ?! - 50

*Après-guerre, la 2ème division blindée a établie ses quartiers très près de l'endroit où a été créé ce challenge.*

*Quelle est la section et la parcelle cadastrale du bâtiment ?*

Dans l'historique de la 2ème DB, on apprend que le QG a été installée en septembre 1946 dans un hôtel particulier au 118 rue de Grenelle. Cela correspond bien à la proximité avec "l'endroit où a été crée ce challenge" (l'École de guerre économique se trouve au 196 rue de Grenelle) et au titre du challenge aussi.

*<img src="/images/2023-BLEUET/2023-05-10 18_22_15-Historique de l’Association _ .png" alt="2023-05-10 18_22_15-Historique de l’Association _ 2e DB - Général LECLERC - 2ème Division Blindée — .png" width="753" height="200" class="jop-noMdConv">*

Ensuite depuis le [site du plan cadastral,](https://www.cadastre.gouv.fr/scpc/authentificationBoite.do) en rentrant l'adresse donnée on obtient la section AX et la parcelle 83.

*<img src="/images/2023-BLEUET/2023-05-10 18_22_07-cadastre.gouv.fr — Mozilla Fir.png" alt="cadastre" width="653"  class="jop-noMdConv">*

*-\> Flag : BLEUET{AX_83}*

### S'armer de patience - 50

*Il aura fallu 565 jours, mais la 2ème division blindée y a enfin eu droit. Mais où donc a-t-elle pu en profiter ?*

*Indiquez les coordonnées GPS en degrés décimaux sous le format suivant.*

La 2ème DB a été créée le 24 août 1943. Si on ajoute 565 jours, on arrive au 11 mars 1945. Cela correspond à la première interprétation de la marche de la 2ème DB au [château de Saint-Germain-en-Laye](https://fr.wikipedia.org/wiki/Ch%C3%A2teau_de_Saint-Germain-en-Laye) ("48° 53′ 53″ nord, 2° 05′ 46″ est" soit 48.89,2.09 en degrés décimaux).

*<img src="/images/2023-BLEUET/2023-05-14 22_41_41-2e division blindée (France) —.png" alt="GPS" class="jop-noMdConv">*


-\> Flag : BLEUET{48.89,2.09}

### La libération de Paris - 100

*La 2e division blindée libère Paris !*

<img src="/images/2023-BLEUET/bcf3b16776a8e087e0699a7568d0b558" alt="Image2.png" width="547" height="281" class="jop-noMdConv">

*Retrouvez le lieu et l’heure (arrondir à la dizaine de minutes) à laquelle cette photographie a été prise.*

Le challenge plus complexe à mon niveau. Pour commencer, pour la localisation générale pas trop de souci : on sait qu'on est à Paris. L'observation de l'image permet de repérer ce qui semble être le dôme des Invalides. Cela est confirmé par une [recherche image inversée](https://www.france-libre.net/2e-db-liberation-paris/) qui permet de rapidement situer le quartier : 

<img src="/images/2023-BLEUET/2023-05-14 22_22_26-La 2e DB et la libération de P.png" alt="Image2.png" width="247" class="jop-noMdConv">

Pour situer plus précisément la scène, sur Streetview j'essaye de reproduire l'angle de la photo. Cela semble être dans la suite du Boulevard des Invalides, peut-être l'avenue de Villars. La distance avec la profondeur de la photo est difficile à évaluer. Je trouve ensuite une [carte postale ancienne de l'Avenue de Villars](https://cartorum.fr/carte-postale/119720/paris-7e-avenue-de-villars-invalides) qui semble plutôt faire pencher la balance de ce coté (on y voit également les rails présents sur notre photo).

Ensuite pour déterminer l'heure, on sait juste que c'est le matin. Pour affiner, j'ai parcouru de nombreux sites et extraits d'ouvrages pour situer les entrées et la chronologie des groupements ([exemple)](https://www.2edb-leclerc.fr/liberation-de-paris-3/). Lequel est passé par les Invalides en remontant du sud ? Il semble s'agir du sous-groupement Rouvillois, partant de la Porte d'Orléans vers 8h30/9h.

<img src="/images/2023-BLEUET/2023-05-07 14_26_40-Libération de Paris – 3 _ 2e D.png" alt="2023-05-07 14_26_40-Libération de Paris – 3 _ 2e DB - Général LECLERC - 2ème Division Blindée — Mozi.png" width="559" height="410" class="jop-noMdConv">

L'ensemble des lectures concernant l'arrivée aux Invalides me font pencher pour un créneau entre 10h et 11h. 

<img src="/images/2023-BLEUET/2023-05-08 01_51_57-Le général Marc Rouvillois_ Ou.png" alt="2023-05-08 01_51_57-Le général Marc Rouvillois_ Ou La victoire en chargeant - Édouard Pellissier - G.png" width="592" height="320" class="jop-noMdConv">

Mais comment affiner à un créneau de 10 minutes ? Tournant en rond, je succombe à l'indice, celui-ci indique d'utiliser les guides & astuces du club, surement le [club OSINT & Veille de l'AEGE](https://www.aege.fr/groupe/club-osint-veille-18). En fouillant les newsletters, je tombe sur [cette ressource](https:/www.portail-ie.fr/univers/osint-et-veille/2023/guide-astuces-osint-5-lutilisation-de-suncalc-pour-horodater-une-image/) pour calculer un créneau horaire approximatif à partir du soleil et des ombres portées. Ca peut aider dans notre cas, on voit ici les ombres, notamment des véhicules. En m'essayant à [Suncalc](https://www.suncalc.org), j'ai ainsi pu réduire le créneau potentiel, sans être absolument certains néanmoins du créneau de 10 minutes.

\- \> Flag : BLEUET{avenue\_de\_villars\_10\_30}

***
## Bonus

### Australie - 25 

*Et comme la mémoire ne concerne pas que la 2ème DB... Quel est le prénom des deux soldats Français décédés en Australie pendant la Première Guerre mondiale ?*

Tout se passe depuis le portail logique pour une recherche de ce type : https://www.memoiredeshommes.sga.defense.gouv.fr/ (Portail culturel du Ministère des Armées). En filtrant les Morts pour la France en Australie lors de la Première Guerre Mondiale, on obtient 5 résultats. En relisant bien l'intitulé de la question, on y parle de "soldats". Il n'y en a que deux (visible en allant sur la fiche détaillée de chacun) : Maroura Maurirere et Tiavairau Teamo.

*<img src="/images/2023-BLEUET/2023-05-12 01_00_52-Faire une recherche - Mémoire .png" alt="2023-05-12 01_00_52-Faire une recherche - Mémoire des hommes.png" width="927" height="463" class="jop-noMdConv">*

-\> Flag : BLEUET{maroura_tiavairau}

### Le Pacha - 75

*Souvent oubliées de l’historiographie de la Seconde Guerre mondiale, des groupes de femmes ayant servi au sein de la 2ème division blindée ont pourtant ouvert les portes de l’armée aux générations féminines suivantes.*

*L’une de ces femmes s’est liée d’amitié avec celui qui a prononcé cette réplique.*

*Quel est le nom de naissance de cette femme et quelle est son année de naissance ?*

Une bande son est en pièce jointe du challenge. On obtient un message inaudible qui semble accéléré. En utilisant le [logiciel d'édition audio Audacity](https://audacity.fr/), et en diminuant la vitesse, des mots commencent à devenir à peu près audible, spécialement "*les cons sur orbite"*. Cela est suffisant pour retrouver l'acteur qui a prononcé [cette réplique](https://www.youtube.com/watch?v=-wawnF9Fkz0) : Jean Gabin dans le film ... Le Pacha", comme le titre du challenge. 

*<img src="/images/2023-BLEUET/2023-05-12 00_36_11-Audio_Bleuet.png" alt="2023-05-12 00_36_11-Audio_Bleuet.png" width="418" height="290" class="jop-noMdConv">*

En associant Gabin et Rochambelles, on obtient des articles de presse relatant la relation avec Marie-Thérèse Tarkoy comme lors de [ses 100 ans célébrés en 2013](https://www.ouest-france.fr/bretagne/vannes-56000/marie-therese-tarkoy-pezet-100-ans-bien-connu-jean-gabin-850219) (née en 1913 donc) : Jean Gabin était le chef de chars de son escadron de fusiliers marin. 

L'avis de décès permet de retrouver le nom de naissance requis : Pezet. 
*<img src="/images/2023-BLEUET/2023-05-12 00_37_46-Avis de décès Marie-Thérèse TA.png" alt="deces" class="jop-noMdConv">*


-\> Flag : BLEUET{pezet_1913}

## Bilan

<img src="/images/2023-BLEUET/AEGE-CTF-2023-Bleuet-final.png" alt="AEGE-CTF-2023-Bleuet-final.png" width="805" height="1406" class="jop-noMdConv">

Pour conclure, **quelques ressources utiles** pour en savoir plus sur la 2ème DB et l'histoire de la libération de Paris : 

- https://www.2edb-leclerc.fr/
- https://liberation-de-paris.gilles-primout.fr
- https://www.voiedela2edb.fr/histoire-de-la-2eme-division-blindee/
- https://www.marinettes-et-rochambelles.com/
- https://2db.forumactif.com
- http://2db.free.fr/