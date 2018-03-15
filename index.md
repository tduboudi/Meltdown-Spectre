# NTIC : les vulnérabilités informatiques matérielles

L'objectif de cette veille technologique était de récolter des informations concernant les vulnérabilitiés informatiques qui ont pour origines des défauts directement liés au matériel ou aux composants informatiques (processeur, RAM, etc.). La présentation qui suit précise un certain nombre de points sur le paysage actuel en cyber-sécurité, avant d'aborder le sujet des vulnérabilités matérielles et de détailler le fonctionnement des failles récemment découverte **Meltdown et Spectre**.

Le domaine de la cyber-sécurité est un champ très actif en informatique, avec chaque jour de nouvelles vulnérabilités corrigées, de nouvelles attaques, etc. Cependant, le domaine des vulnérabilités matérielles est beaucoup plus restreint et la seule activité qu'il y a eu en rapport avec les failles hardware pendant la durée de cette veille était liée, soit à l'apparition de nouvelles variantes de Meltdown et Spectre, soit aux correctifs développés.

# Panorama cyber-sécurité et cyber-menaces actuel  

Les cyber-attaques constituent le quotidien de toutes les organisations, à partir du moment où leur système d'informations atteint une certaine importance. Ces attaques peuvent avoir plusieurs origines et plusieurs objectifs : les attaques peuvent, par exemple, venir d'un virus introduit dans le SI ou bien être mené par ingénierie sociale (phishing) et avoir pour objectif le vol de données sensibles ou bien l'endommagement de services de l'organisation. 

## Les cyber-attaques : une importante source de pertes financières

Dans tous les cas, il résulte d'une attaque réussie une perte financière pour l'entreprise ou l'organisme ciblé : des sanctions légales peuvent être prises si l'attaque résulte d'une infraction aux réglementations, l'entreprise souffre aussi au niveau de son image de marque et une attaque peut décourager les investisseurs ou avoir un impact négatif sur la cotation en bourse de l'entreprise. Enfin, les attaques ont souvent des impacts financiers direct : mise en ligne de 5 films avant leur sortie officielle dans le cas de Sony Pictures (coût total de l'attaque estimé à 101.6 millions de dollars, dont 45 pour la réparation des dégats ([source](https://pedagogie.ec-lyon.fr/claroline/backends/download.php?url=LzIwMTctMjAxOC9Db3Vyc19T6WN1cml06V9kdV9TSV92Mi5wZGY%3D&cidReset=true&cidReq=S9_17160)), vague d'attaques dirigées contre des établissements bancaires : 80 millions de dollars détournés ([source](http://www.lemonde.fr/technologies/article/2012/06/26/80-millions-de-dollars-detournes-dans-une-cyberattaque-visant-des-banques_1724984_651865.html))...

En matière de cyber-criminalité, la tendance est globalement à la hausse et le secteur se porte bien :

D'après PwC ([source](https://www.pwc.fr/fr/espace-presse/communiques-de-presse/2018/fevrier/la-cybercriminalite-devient-la-fraude-la-plus-frequemment-signal.html)) 60% des entreprises françaises ont été victimes de cyber-criminalité sur les 2 dernières années. En deux ans, il s'agit donc d'une progression de 7 points (c'était 53% en 2016).

Mondialement, les données sont les suivantes : 

![Image0](https://github.com/tduboudi/NTIC-Veille-technologique/blob/master/figure1_global_increase.png?raw=true)

![Image](https://github.com/tduboudi/NTIC-Veille-technologique/blob/master/per_country_increase.png?raw=true)

([source](https://www.accenture.com/t20171006T095146Z__w__/us-en/_acnmedia/PDF-62/Accenture-2017CostCybercrime-US-FINAL.pdf))

On constate bien une augmentation généralisée du phénomène, en terme de coûts associés à ces cyber-attaques.

## Les principaux acteurs du milieu


Du côté offensif (cyber-crimes, espionnage économique, vandalisme, déstabilisation, etc.) on trouve plusieurs modèles d'organisations : 

Il existe un certain nombre de groupes, nombreux, bien organisés et bien formés, qui sont essentiellement à l'origine des attaques de grandes ampleurs. Ces groupes agissent parfois pour le compte, ou au moins en lien, avec des états et leurs objectifs consistent le plus souvent à du vol de données sensibles de grande ampleur : c'est le cas de l'attaque contre Sony Pictures, pendant laquelle les assaillants se sont introduits dans le SI de l'entreprise via des failles inconnues et ont  dérobé plusieurs teraoctets de données. Les enquêtes américaines menées après l'attaque ont pointé la responsabilité de la Corée du Nord dans l'opération. Des groupes de ce type sont la plupart du temps à l'origine des attaques les plus sophistiquées, comme en témoigne l'ANSSI ([source](https://www.ssi.gouv.fr/entreprise/principales-menaces/espionnage/)) :

"Le Centre de cyberdéfense constate que ce type d’attaques est le plus souvent le fait de groupes structurés. Ces attaques très ciblées exploitent des codes conçus pour traverser les dispositifs de sécurité techniques de leur cible. Le développement de certains codes malveillants employés requiert parfois de très importants moyens mobilisant des centaines d’ingénieurs. S’agit-il d’États ou de concurrents ? Certaines cyber-attaques utilisent parfois une tactique militaire bien rodée, déployant l’éclaireur, le perceur (intrusion dans le système d’information), celui qui va déposer, celui qui va rechercher, celui qui va collecter et exfiltrer les informations. Dans certaines opérations, le niveau de sophistication technique et la division méthodique du travail mise en place laissent penser que seuls des États ou des organisations dotées d’importants moyens humains et matériels peuvent conduire de telles attaques."

D'autres groupes ont une structuration plus mafieuse et se spécialisent dans le vol de données personnelles, la fraude à des fins d'enrichissement personnel, le phishing ou encore les attaques par ransomware (rançongiciels). C'est le cas de l'organisation, situé en Europe de l'Est et en Russie, à l'origine du malware Zeus, qui permettait, au choix, d'obtenir les identifiants bancaires des victimes ou de crypter des données personnels et de les échanger contre rançons. Son fonctionnement était digne de celui d'une entreprise, avec différentes fonctions au sein de l'organisation : comptable, blanchisseur d'argent, etc. ([source](https://www.wired.com/2017/03/russian-hacker-spy-botnet/)). 

Enfin, on trouve quelques attaques menées par des "hacktivistes" : il s'agit le plus souvent d'attaques visant à destabiliser un organisme dont les attaquants ne partagent pas les convictions : défacement de page web, attaque par déni de service. Par exemple, le collectif Anonymous s'est impliqué dans le conflit israélo-palestinien en attaquant des sites de l'administration israëlienne ([source](https://www.lemonde.fr/proche-orient/article/2012/11/16/anonymous-s-invite-dans-le-conflit-israelo-palestinien_1792141_3218.html)).

Du côté défensif se trouvent un certain nombre d'organismes publics, comme, en France, l'ANSSI (Agence Nationale de la Sécurité des Systèmes d'Informations) chargée de formuler des recommandations à destination des entreprises, ou d'autres organismes et des particuliers et, d'une manière générale, de lutter contre la cyber-criminalité. Mais il existe aussi beaucoup d'acteurs privés : les éditeurs d'antivirus, ou d'autres types de logiciels comme les firewall, par exemple. On trouve aussi des entreprises spécialisés dans l'audit de systèmes d'informations, dans le conseil en sécurité informatique ou même dans la recherche de vulnerabilités, comme Google Project Zero.

Enfin, tous les éditeurs de logiciels, quels qu'ils soient, participent à la sécurité de leurs utilisateurs en prenant en compte les aspects sécurité de leurs produits. Il existe d'autres initiatives moins classiques, comme celle-ci, récente : [Yes We Hack](https://yeswehack.com/fr/index.html). Il s'agit d'une entreprise spécialisée dans le Bug Bounty : une entreprise éditant un logiciel peut décider d'offrir une prime au découvreur d'une faille de sécurité, dépendant de l'importance de celle-ci. Yes We Hack est une entreprise mettant en relations les entreprises offrant les bug bounty et les experts en sécurité susceptible d'y répondre.

## Les grandes familles de vulnérabilités

Une vulnérabilité, ou une faille, correspond à une utilisation non prévue d'un logiciel (ou d'un composant) et qui permet d'obtenir un effet non prévu, potentiellement intéressant pour quelqu'un de malveillant. Il en existe de plusieurs types, qui permettent chacune d'obtenir des choses différentes sur le système ciblé : prise de contrôle totale, accès aux données stockées et manipulées, utilisation comme relai pour communiquer avec d'autres systèmes.

On distingue par exemple les élévations de privilèges, qui consistent à réussir à obtenir des droits sur un système plus élevés que ceux dont on disposait initialement. Cela permet de le modifier en profondeur ou de lui faire faire des choses qui nécessitent habituellement des droits d'administration. Sous Linux, dirty C0w est une faille permettant ainsi d'obtenir les droits root sur un système non protégé.

![Image2](https://proxy.duckduckgo.com/iu/?u=https%3A%2F%2Fi.imgflip.com%2F1zo1th.jpg&f=1)

Un autre type assez classique d'attaque sont les attaques par canaux auxiliaires. Il ne s'agit pas à proprement parler d'exploiter un logiciel d'une manière particulière mais plus d'étudier attentivement son fonctionnement pour en déduire des informations intéressantes. Par exemple, l'image ci-dessous représente la consommation électrique d'un CPU au moment de l'utilisation d'un algorithme de cryptage et permet, connaissant bien l'algorithme utilisé, de retrouver les données manipulées, y compris des clés de chiffrement...

![Image3](https://upload.wikimedia.org/wikipedia/commons/6/6c/Power_attack.png)

Ensuite, une des vulnérabilités les plus classiques est l'erreur de validation d'inputs, qui permet, dans le meilleur des cas, de faire exécuter du code par la machine cible. Les formes les plus connues de ce genre de vulnerabilités sont les injections SQL, ou le cross-site scripting (injections XSS) mais d'autres logiciels ou services y sont vulnérables.

![Image4](https://imgs.xkcd.com/comics/exploits_of_a_mom.png)


## Vers une prise de conscience globale du problème ?

Sur la situation cybersécuritaire actuelle, un constat se fait : la plupart des attaques ont pour origine un problème se trouvant entre la chaise et le clavier. Avec de bonnes pratiques, on peut éviter l'immense majorité des attaques, mais certains reflexes de base ne sont pas encore assez répandu, en témoigne l'accès libre laissé à une base de données de 700 000 lecteurs de "L'Express" ([source](http://www.lemonde.fr/pixels/article/2018/03/01/des-donnees-de-pres-de-700-000-lecteurs-du-site-de-l-express-accessibles-en-ligne_5264341_4408996.html?utm_term=Autofeed&utm_campaign=Echobox&utm_medium=Social&utm_source=Twitter#link_time=1519947848)). 

Cependant, un certain nombre d'initiatives se montent pour faire entrer ces bonnes pratiques dans les pratiques classiques de sécurité, comme celle-ci : https://www.letemps.ch/opinions/une-cyberhygiene-entreprises-genevoises?utm_content=68319697&utm_medium=social&utm_source=twitter.













# Une petite minorité de vulnérabilités : les failles matérielles

## Des failles particulières

Les failles que nous avons mentionné plus haut ont la plupart du temps une origine logicielle, c'est à dire qu'il faut, pour les exploiter, utiliser un logiciel d'une manière particulière. Il arrive aussi que l'exploitation se fasse directement à partir d'un composant du système : CPU, RAM, etc. Elles constituent à l'heure actuelle une minorité de toutes les vulnérabilités existantes, même s'il est difficile de quantifier exactement à quel point car l'organisme en charge de répertorier toutes ces failles (sous la mention CVE, pour Common Vulnerabilities and Exposure) ne permet pas de recherche évidente sur ce critère. La NVD (pour National Vulnerabilities Database), plus complète et détaillée, ne permet pas non plus d'extraire ces informations.

## Difficiles à trouver, difficiles à exploiter et difficiles à corriger

Ces failles, cependant, sont particulièrement complexes à trouver, car elles nécessitent souvent une très bonne connaissance du fonctionnement bas niveau des ordinateurs.  De même, elles sont souvent assez complexes à exploiter (ça n'est pas le cas de Meltdown par exemple). Enfin, elles sont difficiles à corriger, car il faut trouver un correctif logiciel, le plus souvent pour le système d'exploitation, pour un problème matériel. 

À titre d'exemples, quelques-unes des vulnerabilités matérielles les plus connues : 

- Rowhammer (2015) : Les ordinateurs modernes disposent de mécanismes d'isolations de processus : deux programmes différents, en train d'être exécutés, ne peuvent accéder ni en lecture, ni en écriture, aux données manipulées par l'autre. En particulier, un programme ne peut pas accéder aux adresses mémoires réservées au noyau du système d'exploitation. Ce principe d'exclusion permet plus de sureté au niveau de l'exécution des programmes : un programme ne risque pas de modifier les données d'un autre programme accidentellement, mais cela permet aussi d'empêcher "l'espionnage" d'un processus par un autre. Il existe un certain nombre de moyen de briser cette isolation et Rowhammer en est un exemple. Cette faille repose sur le fait que l'accès à une cellule de RAM perturbe électriquement les cellules voisines (avec la diminuation de taille des cellules, il est devenu difficile de les empêcher d'interagir). Avec suffisamment d'accès sur une même cellule, on peut faire changer la valeur du bit stocké dans une cellule voisine. Cette interaction permet de construire une élévation de privilège.

- HSM / TPM Vulnerabilities : un HSM (Hardware Security Module) est un dispositif physique de stockage et de calcul, situé dans certains ordinateurs et indépendants du disque dur, et du CPU, qui permet de gérer et de stocker des clés cryptographique privée. Il existe un certain nombre de vulnérabilité affectant directement ces composants, comme la faille CVE-2015-5464.

- Cold Boot Attack : contrairement à ce qui est régulièrement indiqué, les informations stockées en mémoire RAM ne sont pas effacées à l'arrêt d'un ordinateur. Dans certaines circonstances, elles peuvent persister pendant un certain temps, de quelques secondes à quelques minutes, après l'arrêt du système, et il existe donc des méthodes pour récupérer ces données, sans limitation de droits d'accès. Cette vulnérabilité nécessite un accès physique au système cible et ne constitue donc pas une menace de grande ampleur. Elle est liée au fonctionnement physique de la mémoire RAM : il y a une rémanence des données inhérentes aux mémoires électroniques.

- Meltdown & Spectre : nous en parlerons plus bas.


## Mais qui pourraient devenir plus fréquentes ...

Avec le développement de l'IoT et l'augmentation de la complexité des composants électroniques, relâchés sur le marché dans un contexte de concurrence forte, les étapes de validation de sécurité sont souvent négligées : [70% des objets connectés sont vulnérables aux attaques](http://www8.hp.com/us/en/hp-news/press-release.html?id=1744676). On peut donc craindre une augmentation généralisée des vulnérabilités.












# Meltdown & Spectre

Meltdown et Spectre sont 2 vulnérabilités matérielles rendues publiques début 2018 et qui fait du bruit dans le milieu de la cyber-sécurité parce qu'elles affectent la quasi-totalité des processeurs. L'objectif de cette partie est de présenter le fonctionnement de ces 2 failles d'un point de vue de vulgarisateur, nous n'irons pas le plus profondément possible dans les détails. Tous les détails techniques concernant ces deux attaques sont disponibles [ici](https://meltdownattack.com/).

## Quelques connaissances utiles

Pour comprendre le fonctionnement de Meltdown et de Spectre, il est nécessaire de revenir sur quelques mécanismes bas-niveau des ordinateurs.


#### Exécution spéculative

Contrairement à ce que l'on pourrait penser, un processeur n'exécute pas les instructions se trouvant dans un programme dans l'ordre où elles sont définies. En effet, cette stratégie, qui s'appelle l'exécution spéculative, permet un gain de temps lors de l'exécution qui n'est pas toujours négligeable. C'est un des nombreux mécanismes d'optimisation qui existent sur les processeurs modernes.

Une telle fonctionnalité permet typiquement de continuer l'exécution d'un programme alors qu'il est nécessaire d'aller lire en RAM une valeur. Plutôt que de s'arrêter sur une condition, par exemple, si une lecture en RAM est nécessaire, et d'attendre la réponse de la lecture en RAM, le programme va continuer son exécution. Dès que la réponse est disponible, la condition va être vérifée : si elle est vraie, alors le programme aura bien fait de prendre de l'avance puisque le résultat sera déjà disponible et sinon, il va jeter le résultat et recommencer un calcul correct. 

Elle est gérée directement au niveau firmware et hardware, par des méthodes propriétaires.

#### Mémoire caches

Le stockage des données manipulées par un programme dans un disque dur est une solution qui propose de terribles performances : les temps de lecture et d'écriture sur disque sont trop importants pour avoir quelque chose de suffisamment fonctionnel (voir les performances obtenues avec la swap par exemple). Un programme utilise donc la RAM  (le plus souvent) pour stocker momentanément ses données. 

En pratique, l'accès à une mémoire RAM est aussi trop lente. C'est pour cette raison que les processeurs modernes internes intègrent directement dans leur architecture des mémoires caches (de type L1, L2 ou L3) qui sont des mémoires beaucoup plus coûteuses mais beaucoup plus rapides. Les mémoires de type L1 sont les plus rapides, mais aussi les plus chères donc celles qui stockent le moins d'informations, puis viennent les mémoires caches L2 et L3...

Un programme va donc stocker en cache un certain nombre de données pendant son exécution et notamment les données qu'il manipule le plus souvent. Là encore, la gestion du cache se fait essentiellement à un niveau inférieur à celui du système d'exploitation, mais l'utilisateur a partiellement la main sur le chargement de certaines variables en cache. 


#### Isolation des processus

Enfin, le dernier mécanisme essentiel à la compréhension de nos failles est le mécanisme d'isolation des processus. Nous l'avons abordé dans le paragraphe sur la faille Rowhammer mais nous allons revenir plus en détail sur la manière dont cette isolation est implémenté. 




## Meltdown

---> Reprendre slides et articles

## Spectre

---> Reprendre articles

## Correction

---> Rapidement


## Cas d'utilisation

---> Expliquer le javascript et les VMs



















---------------------------------------------------------------------------------------------------------------------------



Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/tduboudi/Meltdown-Spectre/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
