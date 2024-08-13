Le connecteur source Somtoday simplifie grandement la gestion des comptes utilisateurs et des autorisations au sein de votre organisation éducative. Ce connecteur relie Somtoday à vos systèmes cibles via la solution de Gestion des Identités et Accès (GIA) HelloID de Tools4ever. L'intégration automatise divers processus d'entrée, de transition et de sortie (ETS) au sein de votre organisation, vous libérant ainsi de cette charge. Cet article détaille cette intégration, ses possibilités spécifiques et ses avantages. 

## Qu’est-ce que Somtoday

Somtoday est un environnement numérique d'apprentissage (ENA), un portail offrant aux élèves et aux parents un aperçu des devoirs, des notes, des messages, ainsi que de l'emploi du temps et de la planification des études. Les élèves peuvent également y télécharger et partager des travaux avec leurs enseignants. Somtoday fournit des informations supplémentaires pour les employés et contient toutes les données des participants. Les employés et les élèves utilisent également Somtoday comme environnement de travail. 

## Pourquoi utiliser un connecteur Somtoday ?

Le connecteur Somtoday est souvent utilisé comme source complémentaire à un système RH. Il se concentre spécifiquement sur les participants et la mise à disposition de données supplémentaires sur les employés. De plus, il facilite la gestion des comptes des élèves et des employés. Le connecteur Somtoday permet de se connecter à des systèmes cibles courants, tels que :

*	Active Directory 
*	Entra ID 
*	Google Workspace

Vous trouverez plus de détails sur ces intégrations plus bas.

## Les avantages d'HelloID pour Somtoday :

**Meilleure conformité :** L'intégration améliore également votre conformité. Grâce à l'automatisation, vous garantissez la cohérence des processus et évitez les erreurs. Le contrôle d'accès basé sur les rôles (RBAC) est particulièrement utile, car il vous permet de gérer les autorisations par groupe d'utilisateurs plutôt qu'individuellement. Toutes les modifications effectuées par HelloID sont consignées dans un journal d'audit complet, facilitant ainsi la démonstration de votre conformité.

**Gestion uniforme des comptes :** L'intégration d'un nouvel élève ou employé nécessite la création des comptes appropriés. Grâce à l'intégration de Somtoday avec vos systèmes cibles via HelloID, ce processus est largement automatisé, garantissant une gestion des comptes uniforme et cohérente. Cela évite les erreurs et assure que les utilisateurs disposent des bons comptes au bon moment.

**Adaptation aux processus de l'organisation :** Les établissements éducatifs sont en constante évolution, tant pour les élèves que pour les employés. Les nouvelles personnes arrivent, les élèves passent à une nouvelle année scolaire, les employés changent de poste, et certaines personnes quittent l'organisation. Ces changements nécessitent des mises à jour fréquentes dans vos systèmes, ce qui peut rapidement devenir lourd à gérer. Le connecteur Somtoday simplifie ce travail en automatisant la gestion des comptes pour qu'elle s'adapte parfaitement aux processus ETS de votre organisation.

**Plus grande efficacité :** L'automatisation de la gestion des comptes présente de nombreux avantages. Elle augmente votre efficacité, vous permettant de répondre plus rapidement aux besoins des utilisateurs. Ainsi, les élèves et les employés peuvent accéder plus rapidement aux comptes et aux autorisations dont ils ont besoin.

## Comment HelloID s'intègre avec Somtoday
Lors de l'intégration de Somtoday avec vos systèmes cibles, Somtoday fonctionne généralement comme un complément à votre système RH. Cela permet de gérer automatiquement l'ensemble du cycle de vie des comptes utilisateurs dans vos systèmes cibles via HelloID, réduisant les erreurs, économisant du temps et améliorant le service aux utilisateurs.

| Modification dans Somtoday	| Procédure dans les systèmes cibles |
| -------------------------- | ----------------------------------- | 
| **Nouvel élève ou employé**	| HelloID crée les comptes nécessaires pour les nouveaux élèves et employés dans vos systèmes cibles en se basant sur les informations de Somtoday, et attribue les autorisations requises. Vous n'avez pas à vous en soucier ; HelloID détecte automatiquement les changements dans Somtoday et effectue les mises à jour nécessaires.| 
| **Changement d'année scolaire, de fonction, de placement, de choix de matières et de groupes de cours**	| Les établissements éducatifs sont dynamiques. Les élèves passent à l'année suivante ou redoublent, choisissent de nouvelles matières et se regroupent différemment. Les employés changent également de fonctions. Ces changements peuvent nécessiter de nouveaux comptes et autorisations dans vos systèmes cibles. HelloID automatise largement ce processus, en se basant toujours sur son modèle d'autorisation. Les autorisations liées à l'ancienne fonction sont automatiquement révoquées par HelloID.| 
| **Changement de nom**	| Pour diverses raisons, le nom d'un élève ou d'un employé peut changer. HelloID détecte ce changement et ajuste automatiquement le nom d'utilisateur.| 
| **Départ d'un élève ou employé**	| Les comptes utilisateurs dans les systèmes cibles sont désactivés, et HelloID informe les employés concernés. Après un certain temps, HelloID supprime automatiquement les comptes et révoque les autorisations.| 

HelloID utilise des appels REST standard pour la partie ConnectAPI et des appels SOAP pour la partie HRMService. La solution de GIA récupère les données par établissement et par site pour une année de référence spécifique via la ConnectAPI. Sur cette base, HelloID traite les affectations, les choix de matières et les groupes de cours, afin de les utiliser pour attribuer des autorisations via des règles métiers. La HRMService permet de gérer les données sur la fiche personnelle dans la section RH de Somtoday.

## Connecter Somtoday via HelloID à des systèmes cibles
Vous pouvez connecter Somtoday à divers systèmes cibles via HelloID. Pratique, car HelloID peut ainsi traiter les modifications dans vos systèmes cibles en se basant sur les informations de Somtoday. Ces intégrations vous libèrent de nombreuses tâches et améliorent la gestion des utilisateurs et des autorisations. Voici quelques exemples d'intégrations courantes :

* **Somtoday - Google :** La connexion entre Somtoday et Google permet d'automatiser la gestion des comptes utilisateurs et des autorisations. Lors de la création ou de la modification d'un compte dans Somtoday, HelloID détecte cette modification et la traite automatiquement dans Google, simplifiant ainsi la gestion des comptes.

* **Somtoday - Active Directory :** L'intégration entre Somtoday et Active Directory permet de synchroniser automatiquement ces systèmes, garantissant ainsi que les comptes et les autorisations sont toujours à jour. Vous évitez également les erreurs humaines en n'ayant plus besoin de saisir manuellement les données.

* **Somtoday - Entra ID :** L'intégration avec Entra ID basée sur le cloud permet d'automatiser entièrement tout le processus de provisioning des comptes et d'attribution des autorisations. Si le processus de provisioning a lieu dans Active Directory sur site, vous pouvez également attribuer des permissions uniquement cloud.

HelloID propose environ 200 connecteurs, permettant de relier la solution de GIA à une grande variété de systèmes sources et cibles. Grâce à ces nombreuses possibilités d'intégration, vous pouvez connecter Somtoday à presque tous les systèmes cibles populaires.
