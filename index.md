# NTIC : les vulnérabilités informatiques matérielles

L'objectif de cette veille technologique était de récolter des informations concernant les vulnérabilitiés informatiques qui ont pour origines des défauts directement liés au matériel ou aux composants informatiques (processeur, RAM, etc.). La présentation qui suit précise un certain nombre de points sur le paysage actuel en cyber-sécurité, avant d'aborder le sujet des vulnérabilités matérielles et de détailler le fonctionnement des failles récemment découverte **Meltdown et Spectre**.

# Panorama cyber-sécurité et cyber-menaces actuel  

Les cyber-attaques constituent le quotidien des entreprises ou des organisations, à partir du moment où leur système d'informations atteint une certaine importance. Ces attaques peuvent avoir plusieurs origines et plusieurs objectifs : les attaques peuvent, par exemple, venir d'un virus introduit dans le SI ou bien être mené par ingénierie sociale (phishing) et avoir pour objectif le vol de données sensibles ou bien l'endommagement de services de l'organisation. 

## Les cyber-attaques : une importante source de pertes financières

Dans tous les cas, il résulte d'une attaque réussie une perte financière pour l'entreprise ou l'organisme ciblé : des sanctions légales peuvent être prises si l'attaque résulte d'une infraction aux réglementations, l'entreprise souffre aussi au niveau de son image de marque et une attaque peut décourager les investisseurs ou avoir un impact négatif sur la cotation en bourse de l'entreprise. Enfin, les attaques ont souvent des impacts financiers direct : leaking de films avant leur sortie officielle dans le cas de SONY, paralysie totale de l'organisation dans le cas de la NHS britannique à cause d'un ransomware...[faut justifier ça]

---> Des statistiques

## Les principaux acteurs du milieu


L'image hollywoodienne du hacker travaillant seul dans son grenier n'est plus d'actualité. Du côté offensif se trouvent un certain nombre de groupes, plus ou moins étatiques, bien organisés et bien formés, qui sont à l'origine des attaques utilisant des vulnérabilités inconnues ou 0-day. Les attaques reposant sur le phishing ou les opérations d'ingénierie sociale sont le fruit de groupes moins structurés. [faut justifier ça]

---> L'ère du hacker dans son grenier chez ses parents est terminé

---> Les acteurs étatiques : 

------> Quelques organismes comme l'ANSSI

------> Les services de renseignement

---> Les acteurs privés :

------> Beaucoup d'entreprises actives dans le domaine de la cyber-sécurité / défense

------> Quelques fabricants de logiciels espions

---> Les acteurs illégaux

------> Forte structuration à l'heure actuelle

## Les grandes familles de vulnérabilités

Une vulnérabilité, ou une faille, correspond à une utilisation non prévue d'un logiciel (ou d'un composant) et qui permet d'obtenir un effet non prévu, potentiellement intéressant pour quelqu'un de malveillant. Il en existe de plusieurs types, qui permettent chacune d'obtenir des choses différentes sur le système ciblé : prise de contrôle totale, accès aux données stockées et manipulées, utilisation comme relai pour communiquer avec d'autres systèmes.




---> Qu'est ce qu'une faille ? Une utilisation non prévue d'un logiciel qui permet de faire des choses potentiellement malveillantes...

---> Voir les slides et en rajouter quelques unes.


## Vers une prise de conscience globale du problème ?

---> Un constat : la plupart des problèmes ont pour origine un problème se trouvant entre la chaise et le clavier. Avec de bonnes pratiques, on peut éviter 99% des attaques, mais ça ne semble pas encore bien connu... Cf Trustico, dernier en date.




# Une petite minorité de vulnérabilités : les failles matérielles

## Des failles particulières

---> dont l'origine n'est pas un logiciel mais un composant informatique

## Difficile à trouver, difficile à exploiter et difficile à corriger

---> Elles nécessitent de comprendre le fonctionnement des composants à un niveau très profond. Il faut des équipes et des compétences spécifiques que l'on ne trouve pas partout.


## Mais qui pourraient devenir plus fréquentes ...

---> avec le développement de l'IoT et la prise en compte de la sécurité de manière assez légère on va dire. L'augmentation de composants spécifiques, lâchés sur le marché le plus rapidement possible va dans ce sens.

---> Parler de l'actualité des failles hardware si je trouve quelque chose à dire


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
