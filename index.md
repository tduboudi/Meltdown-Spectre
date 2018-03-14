# NTIC : les vulnérabilités informatiques matérielles

L'objectif de cette veille technologique était de récolter des informations concernant les vulnérabilitiés informatiques qui ont pour origines des défauts directement liés au matériel ou aux composants informatiques (processeur, RAM, etc.). La présentation qui suit précise un certain nombre de points sur le paysage actuel en cyber-sécurité, avant d'aborder le sujet des vulnérabilités matérielles et de détailler le fonctionnement des failles récemment découverte **Meltdown et Spectre**.

Le domaine de la cyber-sécurité est un champ très actif en informatique, avec chaque jour de nouvelles vulnérabilités corrigées, de nouvelles attaques, etc. Cependant, le domaine des vulnérabilités matérielles est beaucoup plus restreint et la seule activité qu'il y a eu en rapport avec les failles hardware pendant la durée de cette veille était liée, soit à l'apparition de nouvelles variantes de Meltdown et Spectre, soit aux correctifs développés.

# Panorama cyber-sécurité et cyber-menaces actuel  

Les cyber-attaques constituent le quotidien de toutes les organisations, à partir du moment où leur système d'informations atteint une certaine importance. Ces attaques peuvent avoir plusieurs origines et plusieurs objectifs : les attaques peuvent, par exemple, venir d'un virus introduit dans le SI ou bien être mené par ingénierie sociale (phishing) et avoir pour objectif le vol de données sensibles ou bien l'endommagement de services de l'organisation. 

## Les cyber-attaques : une importante source de pertes financières

Dans tous les cas, il résulte d'une attaque réussie une perte financière pour l'entreprise ou l'organisme ciblé : des sanctions légales peuvent être prises si l'attaque résulte d'une infraction aux réglementations, l'entreprise souffre aussi au niveau de son image de marque et une attaque peut décourager les investisseurs ou avoir un impact négatif sur la cotation en bourse de l'entreprise. Enfin, les attaques ont souvent des impacts financiers direct : mise en ligne de 5 films avant leur sortie officielle dans le cas de Sony Pictures (coût total de l'attaque estimé à 101.6 millions de dollars, dont 45 pour la réparation des dégats [source](https://pedagogie.ec-lyon.fr/claroline/backends/download.php?url=LzIwMTctMjAxOC9Db3Vyc19T6WN1cml06V9kdV9TSV92Mi5wZGY%3D&cidReset=true&cidReq=S9_17160), vague d'attaques dirigées contre des établissements bancaires : 80 millions de dollars détournés [source](http://www.lemonde.fr/technologies/article/2012/06/26/80-millions-de-dollars-detournes-dans-une-cyberattaque-visant-des-banques_1724984_651865.html)...

En matière de cyber-criminalité, la tendance est globalement à la hausse : 



## Les principaux acteurs du milieu


L'image hollywoodienne du hacker travaillant seul dans son grenier n'est plus d'actualité. Du côté offensif on trouve plusieurs modèles d'organisations : 

Il existe un certain nombre de groupes, bien organisés et bien formés, qui sont à l'origine des attaques utilisant des vulnérabilités inconnues. Ces groupes agissent parfois pour le compte, ou au moins en lien, avec des états et leurs objectifs consistent le plus souvent à du vol de données de grande ampleur : exemple de Sony Pictures, et [trouver d'autres exemples].

D'autres groupes ont une structuration plus mafieuse et se spécialisent dans le vol de données personnelles, ou la fraude à des fins d'enrichissement personnels.

Enfin, d'autres organismes sont spécialisés dans les campagnes de phishing... [faut étoffer ça].


Les attaques reposant sur le phishing ou les opérations d'ingénierie sociale sont le fruit de groupes moins structurés. [faut justifier ça]

DU côté de la cyber-sécurité, ou de la cyber-défense se trouvent un certain nombre d'organismes publics, comme, en France, l'ANSSI (Agence Nationale de la Sécurité des Systèmes d'Informations) chargée de formuler des recommandations à destination des entreprises, ou d'autres organismes et des particuliers et, d'une manière générale, de lutter contre la cyber-criminalité. Mais il existe aussi beaucoup d'acteurs privés : les éditeurs d'antivirus, ou d'autres types de logiciels comme les firewall, par exemple. On trouve aussi des entreprises spécialisés dans l'audit de systèmes d'informations ou dans le conseil en sécurité informatique. Enfin, tous les éditeurs de logiciels, quels qu'ils soient, participent à la sécurité de leurs utilisateurs en prenant en compte les aspects sécurité de leurs produits. Enfin, il existe d'autres initiatives moins classiques, comme celle-ci, récente : [insérier liens ici].

Il s'agit d'une entreprise spécialisée dans le Bug Bounty [expliquer le principe du bug bounty ici].

## Les grandes familles de vulnérabilités

Une vulnérabilité, ou une faille, correspond à une utilisation non prévue d'un logiciel (ou d'un composant) et qui permet d'obtenir un effet non prévu, potentiellement intéressant pour quelqu'un de malveillant. Il en existe de plusieurs types, qui permettent chacune d'obtenir des choses différentes sur le système ciblé : prise de contrôle totale, accès aux données stockées et manipulées, utilisation comme relai pour communiquer avec d'autres systèmes.

---> Voir les slides et en rajouter quelques unes.


## Vers une prise de conscience globale du problème ?

---> Un constat : la plupart des problèmes ont pour origine un problème se trouvant entre la chaise et le clavier. Avec de bonnes pratiques, on peut éviter 99% des attaques, mais ça ne semble pas encore bien connu... [Cf Trustico, dernier en date].














































































































# Une petite minorité de vulnérabilités : les failles matérielles

## Des failles particulières

---> dont l'origine n'est pas un logiciel mais un composant informatique

## Difficile à trouver, difficile à exploiter et difficile à corriger

---> Elles nécessitent de comprendre le fonctionnement des composants à un niveau très profond. Il faut des équipes et des compétences spécifiques que l'on ne trouve pas partout.


## Mais qui pourraient devenir plus fréquentes ...

---> avec le développement de l'IoT et la prise en compte de la sécurité de manière assez légère on va dire. L'augmentation de composants spécifiques, lâchés sur le marché le plus rapidement possible va dans ce sens.

---> Parler de l'actualité des failles hardware si je trouve quelque chose à dir


# Meltdown & Spectre

## Quelques connaissances utiles

---> Exécution spéculative

---> Mémoire caches

---> Isolation des processus


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
