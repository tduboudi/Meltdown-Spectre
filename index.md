# NTIC : les vulnérabilités informatiques matérielles

L'objectif de cette veille technologique était de récolter des informations concernant les vulnérabilitiés informatiques qui ont pour origines des défauts directement liés au matériel ou aux composants informatiques (processeur, RAM, etc.). La présentation qui suit précise un certain nombre de points sur le paysage actuel en cyber-sécurité, avant d'aborder le sujet des vulnérabilités matérielles et de détailler le fonctionnement des failles récemment découverte **Meltdown et Spectre**.

Le domaine de la cyber-sécurité est un champ très actif en informatique, avec chaque jour de nouvelles vulnérabilités corrigées, de nouvelles attaques, etc. Cependant, le domaine des vulnérabilités matérielles est beaucoup plus restreint et la seule activité qu'il y a eu en rapport avec les failles hardware pendant la durée de cette veille était liée, soit à l'apparition de nouvelles variantes de Meltdown et Spectre, soit aux correctifs développés.

# Panorama cyber-sécurité et cyber-menaces actuel  

Les cyber-attaques constituent le quotidien de toutes les organisations, à partir du moment où leur système d'informations atteint une certaine importance. Ces attaques peuvent avoir plusieurs origines et plusieurs objectifs : les attaques peuvent, par exemple, venir d'un virus introduit dans le SI ou bien être mené par ingénierie sociale (phishing) et avoir pour objectif le vol de données sensibles ou bien l'endommagement de services de l'organisation. 

## Les cyber-attaques : une importante source de pertes financières

Dans tous les cas, il résulte d'une attaque réussie une perte financière pour l'entreprise ou l'organisme ciblé : des sanctions légales peuvent être prises si l'attaque résulte d'une infraction aux réglementations, l'entreprise souffre aussi au niveau de son image de marque et une attaque peut décourager les investisseurs ou avoir un impact négatif sur la cotation en bourse de l'entreprise. Enfin, les attaques ont souvent des impacts financiers direct : mise en ligne de 5 films avant leur sortie officielle dans le cas de Sony Pictures (coût total de l'attaque estimé à 101.6 millions de dollars, dont 45 pour la réparation des dégats ([source : plateforme pédagogique](https://pedagogie.ec-lyon.fr/claroline/backends/download.php?url=LzIwMTctMjAxOC9Db3Vyc19T6WN1cml06V9kdV9TSV92Mi5wZGY%3D&cidReset=true&cidReq=S9_17160)), vague d'attaques dirigées contre des établissements bancaires : 80 millions de dollars détournés ([source : Le Monde](http://www.lemonde.fr/technologies/article/2012/06/26/80-millions-de-dollars-detournes-dans-une-cyberattaque-visant-des-banques_1724984_651865.html))...

En matière de cyber-criminalité, la tendance est globalement à la hausse et le secteur se porte bien :

D'après PwC ([source](https://www.pwc.fr/fr/espace-presse/communiques-de-presse/2018/fevrier/la-cybercriminalite-devient-la-fraude-la-plus-frequemment-signal.html)) 60% des entreprises françaises ont été victimes de cyber-criminalité sur les 2 dernières années. En deux ans, il s'agit donc d'une progression de 7 points (53% en 2016).

Mondialement, les données sont les suivantes : 

![Image0](https://github.com/tduboudi/NTIC-Veille-technologique/blob/master/figure1_global_increase.png?raw=true)

![Image](https://github.com/tduboudi/NTIC-Veille-technologique/blob/master/per_country_increase.png?raw=true)

([source : Accenture](https://www.accenture.com/t20171006T095146Z__w__/us-en/_acnmedia/PDF-62/Accenture-2017CostCybercrime-US-FINAL.pdf))

On constate bien une augmentation généralisée du phénomène, en terme de coûts associés à ces cyber-attaques.

## Les principaux acteurs du milieu

```
Du côté offensif (cyber-crimes, espionnage économique, vandalisme, déstabilisation, etc.) on trouve plusieurs modèles d'organisations : 

Il existe un certain nombre de groupes, nombreux, bien organisés et bien formés, qui sont essentiellement à l'origine des attaques de grandes ampleurs. Ces groupes agissent parfois pour le compte, ou au moins en lien, avec des états et leurs objectifs consistent le plus souvent à du vol de données sensibles de grande ampleur : c'est le cas de l'attaque contre Sony Pictures, pendant laquelle les assaillants se sont introduits dans le SI de l'entreprise via des failles inconnues et ont  dérobé plusieurs teraoctets de données. Les enquêtes américaines menées après l'attaque ont pointé la responsabilité de la Corée du Nord dans l'opération. Des groupes de ce type sont la plupart du temps à l'origine des attaques les plus sophistiquées, comme en témoigne l'ANSSI ([source](https://www.ssi.gouv.fr/entreprise/principales-menaces/espionnage/)) :

"Le Centre de cyberdéfense constate que ce type d’attaques est le plus souvent le fait de groupes structurés. Ces attaques très ciblées exploitent des codes conçus pour traverser les dispositifs de sécurité techniques de leur cible. Le développement de certains codes malveillants employés requiert parfois de très importants moyens mobilisant des centaines d’ingénieurs. S’agit-il d’États ou de concurrents ? Certaines cyber-attaques utilisent parfois une tactique militaire bien rodée, déployant l’éclaireur, le perceur (intrusion dans le système d’information), celui qui va déposer, celui qui va rechercher, celui qui va collecter et exfiltrer les informations. Dans certaines opérations, le niveau de sophistication technique et la division méthodique du travail mise en place laissent penser que seuls des États ou des organisations dotées d’importants moyens humains et matériels peuvent conduire de telles attaques."

D'autres groupes ont une structuration plus mafieuse et se spécialisent dans le vol de données personnelles, la fraude à des fins d'enrichissement personnel, le phishing ou encore les attaques par ransomware (rançongiciels). C'est le cas de l'organisation, situé en Europe de l'Est et en Russie, à l'origine du malware Zeus, qui permettait, au choix, d'obtenir les identifiants bancaires des victimes ou de crypter des données personnelles et de les échanger contre rançons. Son fonctionnement était digne de celui d'une entreprise, avec différentes fonctions au sein de l'organisation : comptable, blanchisseur d'argent, etc. ([source : Wired](https://www.wired.com/2017/03/russian-hacker-spy-botnet/)). 

Enfin, on trouve quelques attaques menées par des "hacktivistes" : il s'agit le plus souvent d'attaques visant à destabiliser un organisme dont les attaquants ne partagent pas les convictions : défacement de page web, attaque par déni de service. Par exemple, le collectif Anonymous s'est impliqué dans le conflit israélo-palestinien en attaquant des sites de l'administration israëlienne ([source : Le Monde](https://www.lemonde.fr/proche-orient/article/2012/11/16/anonymous-s-invite-dans-le-conflit-israelo-palestinien_1792141_3218.html)).

Du côté défensif se trouvent un certain nombre d'organismes publics, comme, en France, l'ANSSI (Agence Nationale de la Sécurité des Systèmes d'Informations) chargée de formuler des recommandations à destination des entreprises, ou d'autres organismes et des particuliers et, d'une manière générale, de lutter contre la cyber-criminalité. Mais il existe aussi beaucoup d'acteurs privés : les éditeurs d'antivirus, ou d'autres types de logiciels comme les firewall, par exemple. On trouve aussi des entreprises spécialisées dans l'audit de systèmes d'informations, dans le conseil en sécurité informatique ou même dans la recherche de vulnerabilités, comme Google Project Zero.

Enfin, tous les éditeurs de logiciels, quels qu'ils soient, participent à la sécurité de leurs utilisateurs en prenant en compte les aspects sécurité de leurs produits. Il existe d'autres initiatives moins classiques, comme celle-ci, récente : [Yes We Hack](https://yeswehack.com/fr/index.html). Il s'agit d'une entreprise spécialisée dans le Bug Bounty : une entreprise éditant un logiciel peut décider d'offrir une prime au découvreur d'une faille de sécurité, dépendant de l'importance de celle-ci. Yes We Hack est une entreprise mettant en relations les entreprises offrant les bug bounty et les experts en sécurité susceptibles d'y répondre.
```

## Les grandes familles de vulnérabilités

```
Une vulnérabilité, ou une faille, correspond à une utilisation non prévue d'un logiciel (ou d'un composant) et qui permet d'obtenir un effet non prévu, potentiellement intéressant pour quelqu'un de malveillant. Il en existe de plusieurs types, qui permettent chacune d'obtenir des choses différentes sur le système ciblé : prise de contrôle totale, accès aux données stockées et manipulées, utilisation comme relai pour communiquer avec d'autres systèmes, etc.

On distingue par exemple les élévations de privilèges, qui consistent à réussir à obtenir des droits sur un système plus élevés que ceux dont on disposait initialement. Cela permet de le modifier en profondeur ou de lui faire faire des choses qui nécessitent habituellement des droits d'administration. Sous Linux, dirty C0w est une faille permettant ainsi d'obtenir les droits root sur un système non protégé.

![Image2](https://proxy.duckduckgo.com/iu/?u=https%3A%2F%2Fi.imgflip.com%2F1zo1th.jpg&f=1)

Un autre type assez classique d'attaque sont les attaques par canaux auxiliaires. Il ne s'agit pas à proprement parler d'exploiter un logiciel d'une manière particulière mais plus d'étudier attentivement son fonctionnement pour en déduire des informations intéressantes. Par exemple, l'image ci-dessous représente la consommation électrique d'un CPU au moment de l'utilisation d'un algorithme de cryptage et permet, connaissant bien l'algorithme utilisé, de retrouver les données manipulées, y compris des clés de chiffrement...

![Image3](https://upload.wikimedia.org/wikipedia/commons/6/6c/Power_attack.png)

([source : wikipédia](https://en.wikipedia.org/wiki/Side-channel_attack))

Ensuite, une des vulnérabilités les plus classiques est l'erreur de validation d'inputs, qui permet, dans le meilleur des cas, de faire exécuter du code par la machine cible. Les formes les plus connues de ce genre de vulnerabilités sont les injections SQL, ou le cross-site scripting (injections XSS) mais d'autres logiciels ou services y sont vulnérables.

![Image4](https://imgs.xkcd.com/comics/exploits_of_a_mom.png)

([source : xkcd](https://www.xkcd.com/))
```

## Vers une prise de conscience globale du problème ?

Sur la situation cyber-sécuritaire actuelle, un constat se fait : la plupart des attaques ont pour origine un problème se trouvant entre la chaise et le clavier. Avec de bonnes pratiques, on peut éviter l'immense majorité des attaques, mais certains reflexes de base ne sont pas encore assez répandus, en témoigne l'accès libre laissé à une base de données de 700 000 lecteurs de "L'Express" ([source : Pixel (Le Monde)](http://www.lemonde.fr/pixels/article/2018/03/01/des-donnees-de-pres-de-700-000-lecteurs-du-site-de-l-express-accessibles-en-ligne_5264341_4408996.html?utm_term=Autofeed&utm_campaign=Echobox&utm_medium=Social&utm_source=Twitter#link_time=1519947848)). 

Cependant, un certain nombre d'initiatives se montent pour faire entrer ces bonnes pratiques dans les pratiques classiques de sécurité, comme celle-ci : [https://www.letemps.ch/opinions/une-cyberhygiene-entreprises-genevoises?utm_content=68319697&utm_medium=social&utm_source=twitter](https://www.letemps.ch/opinions/une-cyberhygiene-entreprises-genevoises?utm_content=68319697&utm_medium=social&utm_source=twitter).













# Une petite minorité de vulnérabilités : les failles matérielles

## Des failles particulières

Les failles que nous avons mentionné plus haut ont la plupart du temps une origine logicielle, c'est à dire qu'il faut, pour les exploiter, utiliser un logiciel d'une manière particulière. Il arrive aussi que l'exploitation se fasse directement à partir d'un composant du système : CPU, RAM, etc. Elles constituent à l'heure actuelle une minorité de toutes les vulnérabilités existantes, même s'il est difficile de quantifier exactement à quel point car l'organisme en charge de répertorier toutes ces failles (sous la mention CVE, pour [Common Vulnerabilities and Exposure](https://cve.mitre.org/) ne permet pas de recherche évidente sur ce critère. La NVD (pour National Vulnerabilities Database), plus détaillée, ne permet pas non plus d'extraire ces informations.

## Difficiles à trouver, difficiles à exploiter et difficiles à corriger

Ces failles, cependant, sont particulièrement complexes à trouver, car elles nécessitent souvent une très bonne connaissance du fonctionnement bas niveau des ordinateurs.  De même, elles sont souvent assez complexes à exploiter (ça n'est pas le cas de Meltdown par exemple). Enfin, elles sont difficiles à corriger, car il faut trouver un correctif logiciel, le plus souvent pour le système d'exploitation, pour un problème matériel. 

```
À titre d'exemples, quelques-unes des vulnerabilités matérielles les plus connues : 

- [Rowhammer](https://googleprojectzero.blogspot.fr/2015/03/exploiting-dram-rowhammer-bug-to-gain.html) (2015) : Les ordinateurs modernes disposent de mécanismes d'isolations de processus : deux programmes différents, en train d'être exécutés, ne peuvent accéder ni en lecture, ni en écriture, aux données manipulées par l'autre. En particulier, un programme ne peut pas accéder aux adresses mémoires réservées au noyau du système d'exploitation. Ce principe d'exclusion permet plus de sureté au niveau de l'exécution des programmes : un programme ne risque pas de modifier les données d'un autre programme accidentellement, mais cela permet aussi d'empêcher "l'espionnage" d'un processus par un autre. Il existe un certain nombre de moyen de briser cette isolation et Rowhammer en est un exemple. Cette faille repose sur le fait que l'accès à une cellule de RAM perturbe électriquement les cellules voisines (avec la diminuation de taille des cellules, il est devenu difficile de les empêcher d'interagir). Avec suffisamment d'accès sur une même cellule, on peut faire changer la valeur du bit stocké dans une cellule voisine. Cette interaction permet de construire une élévation de privilège.

- HSM / TPM Vulnerabilities : un HSM (Hardware Security Module) est un dispositif physique de stockage et de calcul, situé dans certains ordinateurs et indépendants du disque dur, et du CPU, qui permet de gérer et de stocker des clés cryptographique privée. Il existe un certain nombre de vulnérabilité affectant directement ces composants, comme la faille [CVE-2015-5464](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5464).

- [Cold Boot Attack](https://en.wikipedia.org/wiki/Cold_boot_attack) : contrairement à ce qui est régulièrement indiqué, les informations stockées en mémoire RAM ne sont pas effacées à l'arrêt d'un ordinateur. Dans certaines circonstances, elles peuvent persister pendant un certain temps, de quelques secondes à quelques minutes, après l'arrêt du système, et il existe donc des méthodes pour récupérer ces données, sans limitation de droits d'accès. Cette vulnérabilité nécessite un accès physique au système cible et ne constitue donc pas une menace de grande ampleur. Elle est liée au fonctionnement physique de la mémoire RAM : il y a une rémanence des données inhérentes aux mémoires électroniques.

- Meltdown & Spectre : nous en parlerons plus bas.
```

## Mais qui pourraient devenir plus fréquentes ...

Avec le développement de l'IoT et l'augmentation de la complexité des composants électroniques, relâchés sur le marché dans un contexte de concurrence forte, les étapes de validation de sécurité sont souvent négligées : [70% des objets connectés sont vulnérables aux attaques](http://www8.hp.com/us/en/hp-news/press-release.html?id=1744676). On peut donc craindre une augmentation généralisée des vulnérabilités.












# Meltdown & Spectre

Meltdown et Spectre sont 2 vulnérabilités matérielles rendues publiques début 2018 et qui ont fait du bruit dans le milieu de la cyber-sécurité parce qu'elles affectent la quasi-totalité des processeurs. L'objectif de cette partie est de présenter le fonctionnement de ces 2 failles d'un point de vue de vulgarisateur, nous n'irons pas le plus profondément possible dans les détails. Tous les détails techniques concernant ces deux attaques sont disponibles [ici](https://meltdownattack.com/).

## Quelques connaissances utiles

Pour comprendre le fonctionnement de Meltdown et de Spectre, il est nécessaire de revenir sur quelques mécanismes bas niveau des ordinateurs.


#### Exécution spéculative

Contrairement à ce que l'on pourrait penser, un processeur n'exécute pas les instructions se trouvant dans un programme dans l'ordre où elles sont définies. En effet, cette stratégie, qui s'appelle l'exécution spéculative, permet un gain de temps lors de l'exécution qui n'est pas toujours négligeable. C'est un des nombreux mécanismes d'optimisation qui existent sur les processeurs modernes.

Une telle fonctionnalité permet typiquement de continuer l'exécution d'un programme alors qu'il est nécessaire d'aller lire en RAM une valeur. Plutôt que de s'arrêter sur une condition, par exemple, si une lecture en RAM est nécessaire, et d'attendre la réponse de la lecture en RAM, le programme va continuer son exécution. Dès que la réponse est disponible, la condition va être vérifée : si elle est vraie, alors le programme aura bien fait de prendre de l'avance puisque le résultat sera déjà disponible et sinon, il va jeter le résultat et recommencer un calcul correct. 

![Image_xkcd_2](https://imgs.xkcd.com/comics/meltdown_and_spectre_2x.png)

(source : xkcd)

L'exécution spéculative est gérée directement au niveau firmware et hardware, par des méthodes propriétaires.

#### Mémoire caches

Le stockage des données manipulées par un programme dans un disque dur est une solution qui propose de terribles performances : les temps de lecture et d'écriture sur disque sont trop importants pour avoir quelque chose de suffisamment fonctionnel (voir les performances obtenues avec la swap par exemple). Un programme utilise donc la RAM  (le plus souvent) pour stocker momentanément ses données. 

En pratique, l'accès à une mémoire RAM est aussi trop lente. C'est pour cette raison que les processeurs modernes internes intègrent directement dans leur architecture des mémoires caches (de type L1, L2 ou L3) qui sont des mémoires beaucoup plus coûteuses mais beaucoup plus rapides. Les mémoires de type L1 sont les plus rapides, mais aussi les plus chères donc celles qui stockent le moins d'informations, puis viennent les mémoires caches L2 et L3...

![imagebb](https://cdn-images-1.medium.com/max/800/1*Su7d0UCcqBSgeYHdpmGRdg.png)

([source : https://medium.com/@mattklein123/meltdown-spectre-explained-6bc8634cc0c2](https://medium.com/@mattklein123/meltdown-spectre-explained-6bc8634cc0c2))

Un programme va donc stocker en cache un certain nombre de données pendant son exécution et notamment les données qu'il manipule le plus souvent. Là encore, la gestion du cache se fait essentiellement à un niveau inférieur à celui du système d'exploitation, mais l'utilisateur a partiellement la main sur le chargement de certaines variables en cache. 


#### Isolation des processus

Enfin, le dernier mécanisme essentiel à la compréhension de nos failles est le mécanisme d'isolation des processus. Nous l'avons abordé dans le paragraphe sur la faille Rowhammer mais nous allons revenir plus en détail sur la manière dont cette isolation est implémentée. 

L'isolation de processus repose principalement sur un mécanisme appelé **Mémoire virtuelle**. Ce mécanisme effectue une "traduction" à la volée des adresses mémoires vues et manipulées par un programme vers des adresses mémoires de la mémoire physique. On parle donc de mémoire virtuelle puisque les adresses vues par un programme ne correspondent à des adresses mémoires réelles.

![image_n](https://upload.wikimedia.org/wikipedia/commons/thumb/f/ff/Memoire_virtuelle.svg/330px-Memoire_virtuelle.svg.png)

La manière dont cette "traduction" est réalisée (des segments de mémoire réelle disjoints sont alloués aux différents programmes, même si du côté mémoire virtuelle, ils utilisent les mêmes plages d'adresses) permet d'obtenir l'isolation des processus. Elle est réalisée directement par des composants électroniques et non pas par le système d'exploitation pour des raisons de performances.



## Cas d'utilisation


Meltdown et Spectre sont des failles qui peuvent être utilisées pour "espionner" des données se trouvant en mémoire vive. Il est cependant nécessaire de réussir à exécuter le code d'attaque sur la machine cible. Hors il est assez compliqué d'obtenir d'une machine sur laquelle nous n'avons pas de droits qu'elle exécute le code de notre choix. À deux exceptions près : **le javascript** présent sur une page web et qui est exécuté par le navigateur de la machine consultant la page, et **les machines virtuelles** qui permettent d'exécuter sur le même matériel que la machine virtuelle cible un code de notre choix. En effet, grâce à ces failles, on peut réussir à lire les données manipulées par des machines virtuelles différentes de celle sur laquelle s'exécute le code malicieux étant donné qu'elles partagent le même matériel physique. Meltdown et Spectre donc une préoccupation importante pour les éditeurs de navigateur web, comme Firefox ou Google Chrome, et pour les entreprises proposant des services cloud comme Amazon Web Service, Microsoft Azure ou Google Cloud pour les plus connues.

## Meltdown

Nous pouvons donc maintenant rentrer dans le vif du sujet et aborder la première vulnérabilité : Meltdown.

Il s'agit d'une vulnérabilité qui permet de briser l'isolation des processus par l'utilisation d'un canal auxiliaire (Side Channel Attack, en anglais). Elle permet donc de lire en mémoire vive des données appartenant à d'autres processus, voir même au noyau du système d'exploitation. En revanche, elle ne permet pas d'écrire quoi que ce soit, c'est purement un outil destiné à l'espionnage ou au vol de données sensibles, comme des mots de passe par exemple. 

Elle a été découverte relativement indépendamment par des chercheurs du Google Project Zero (Jann Horn notamment) et des chercheurs de Cyberus Technology (Werner Haas, Thomas Prescher) ainsi que des chercheurs de l'université technologique de Graz (Daniel Gruss, Moritz Lipp, Stefan Mangard, Michael Schwarz). Elle cible tous les ordinateurs disposant de processeurs Intel, et certaines puces ARM y sont aussi vulnérables. Les entreprises concernées (Intel, quelques fabricants de puces ARM, mais aussi éditeurs de systèmes d'exploitations et entreprises spécialisées en cyber-sécurité) sont prévenues le 28 juillet 2017, et la vulnérabilité est rendue publique le 3 janvier 2018 (initialement la divulgation était prévue le 9 janvier mais des fuites et des pressions sur Intel ont acceléré le processus). Le délai s'explique simplement par la nécessité de développer un correctif avant de révéler l'existence de la vulnérabilité, sous peine de la voir utilisée à des fins malveillantes.

```
Son mode de fonctionnement est le suivant : 

1. On commence par créer un tableau de 256 cases (256 pour toutes les valeurs que peut prendre un octet), qui va servir de receptacle de l'attaque

2. Par des méthodes que nous ne détaillerons pas, on peut empêcher le processeur de placer les adresses du tableau en mémoire cache. La plus simple consiste à utiliser des instructions bas niveau pour vider certaines adresses du cache.

3. Ensuite, on va tenter de lire l'adresse mémoire cible, une adresse donc qui appartient à un autre programme ou au noyau de l'OS. Cette lecture est interdite, elle va donc provoquer le lancement d'une exception et, en temps normal, la terminaison du programme (on parle de page fault). Cependant, grâce à l'exécution spéculative, cette exception ne va pas être lancée immédiatement.

4. Avant la page fault, on lit la valeur du tableau initial se trouvant à l'index égal à l'octet cible, obtenu à l'étape précédente. Cette étape n'est pas anodine car elle permet en fait de stocker en cache l'adresse mémoire lue.

5. L'utilisation de l'adresse déclenche nécessairement la page fault, mais celle-ci est interceptée. Cependant, le résultat de l'exécution spéculative, c'est à dire l'adresse mémoire lue correspondant à la valeur de l'octet cible, est toujours situé en cache, il n'y a pas eu d'effacement du cache au moment de l'exception.

6. Finalement, on va parcourir le tableau initial et mesurer le temps nécessaire à lecture des informations qui y sont stockées. L'index qui charge le plus rapidement sera celui qui était situé en cache et non en RAM, et comme nous avons bien fait attention à ne pas mettre d'adresses du tableau en cache, cela correspond nécessairement à la valeur de l'octet cible.
```

Nous avons donc pu obtenir la valeur d'un octet de mémoire appartenant à un autre programme : il y a un défaut dans la manière dont l'exécution spéculative est implémenté au niveau des composants.

Meltdown permet de lire des données structurées et de reconstruire même des informations complexes commes des photos ou des mots de passe : 

<iframe width="640" height="480" src="https://www.youtube.com/embed/RbHbFkh6eeE" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

<iframe width="640" height="480" src="https://www.youtube.com/embed/L1N1P2zxaZE" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## Correction

Meltdown est une vulnérabilité qui est à l'heure actuelle corrigée par la totalité des systèmes d'exploitation et des mécanismes supplémentaires ont été introduits dans les navigateurs garantissent la résistance à cette faille de la quasi-totalité des systèmes vis à vis des attaques venant du javascript.

Le correctif repose sur une technique appelée KPTI (Kernel Page Table Isolation) et qui a pour conséquence de limiter l'exécution spéculative sur certains programmes, ce qui se traduit par des pertes de performances : initialement, les pertes étaient estimées allant de 5% à 30%, il semble que ce soit en général moins que ça ([source : wikipédia](https://en.wikipedia.org/wiki/Meltdown_(security_vulnerability)))

## Spectre

Spectre, par rapport à Meltdown, est nettement plus complexe à utiliser mais aussi nettement plus complexe à corriger. Cette faille a été découverte par les mêmes équipes que celles à l'origine de Meltdown, et présentée aux fabricants de puces et aux éditeurs de systèmes d'exploitation quasiment en même temps que Meltdown. À la différence de Meltdown par contre, elle affecte la totalité des processeurs présents sur le marché (ou l'immense majorité) puisque Intel, AMD, les puces ARM et les processeurs d'IBM y sont vulnérables. 

Son fonctionnement repose essentiellement sur un autre mécanisme d'optimisation, proche de l'exécution spéculative utilisée par Meltdown, qui s'appelle la prédiction de branchement : devant une condition, avec plusieurs issues, un processeur moderne va spéculer sur le résultat de cette condition (sa valeur et sa localisation en mémoire notamment) et effectuer les calculs correspondant à sa prédiction.

Spectre est une méthode qui va chercher à induire en erreur ce mécanisme de prédiction, par exemple en répétant un grand nombre de fois la même condition, avec le même résultat. Comme précédemment avec Meltdown, l'erreur de prédiction permet de lire une adresse mémoire normalement inaccessible et interdite. Et par diverses méthodes, similaires à celle de Meltdown, on peut récupérer la valeur de l'adresse interdite après que le processeur se soit rendu compte de son erreur.

La différence principale avec Meltdwon réside dans le fait que Spectre n'est pas un bug : il faut "convaincre" et "tromper" le processeur pour le faire spéculer de manière incorrecte (par exemple avec la boucle mentionnée plus haut) et exploiter cette erreur, il n'y a pas de problèmes de conception dans la méthode de prédiction de branche, là où l'exécution spéculative de Meltdown ne devrait pas pouvoir avoir lieu pour des questions de droits d'accès. Les algorithmes de prédiction de branchement sont dépendants des constructeurs et c'est en partie pour cette raisons que la faille est plus complexe à mettre en oeuvre : il n'existe pas de méthode universelle pour tromper le mécanisme de prédiction.

## Correction

Contrairement à Meltdown dont les correctifs sont sortis pour toutes les plate-formes, la situation pour Spectre est nettement moins évidente. Spectre peut utiliser plusieurs vecteurs de lecture des données, qui peuvent être spécifique à la plate-forme, et tous les processeurs n'y sont pas encore résistants.

L'approche la plus réussie jusqu'à présent est la technique développée par Google appelée RetPoline (pour ReturnTrampoline) qui permet de résoudre le problème sur la plupart des processeurs utilisants les instructions x86, et ce à un coût très faible en terme de pertes de performances.


# Impact des vulnérabilités

Meltdown et Spectre, à l'inverse des vulnérabilités classiques qui sont vite oubliée, vont sans doute avoir un fort impact sur la manière dont la sécurité est pensée lors des étapes de conception de composants électroniques : avec Rowhammer, ce sont les failles qui affectent le plus de systèmes et pour lesquelles il n'existe pas toujours de correctifs... 

Pour aller plus loin : 

Les articles de l'équipe de chercheurs sur [Meltdown](https://meltdownattack.com/meltdown.pdf) et [Spectre](https://spectreattack.com/spectre.pdf).


---------------------------------------------------------------------------------------------------------------------------
