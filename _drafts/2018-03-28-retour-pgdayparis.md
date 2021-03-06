---
layout: post
title: Retour sur le Pgday Paris 2018
author: David Bidoc
twitter_id: dalibo
github_id: dalibo
tags: [opensource, postgresql, pgday, paris, 2018, conférences, france]
---

---
*Paris, le 28 mars 2018*


### 9h10 : De-mystifying contributing to PostgreSQL

_Laetitia Avrot_, DBA PostgreSQL depuis dix ans chez Loxodata nous a animé une conférence sur la manière dont chacun peut contribuer au développement et à l’amélioration de PostgreSQL.
Laetitia nous a d’abord présenté les différents acteurs de la communauté PostgreSQL :
  * La **Core Team**
  * Les **Commiters**
  * Les **développers et reviewers**
Elle nous a présenté le **Commitfest**.
Elle nous a ensuite présenté la manière à laquelle sont validés les patchs PostgreSQL en nous montrant un exemple de sa propre contribution.




### 10h15 : Constraints: a Developer's Secret Weapon

_Will Leinweber_, Ingénieur a Citus Data nous a présenté les bonnes pratiques d'utilisation des contraintes.
Will nous a parlé de différents types de données pas souvent utilisé, mais qui sont pourtant très utiles tels uuid , macaddr, net et de contraintes très pratiques telles que **CHECK**, **PERCENT** et **EXCLUSION**

La principale motivation pour bien préparer ces contraintes est de se dire que le type de données est la dernière ligne de défense de la base (**Datatype are last line of defense**).



### 11h10 : Being a better developer with Explain

Au cours de cette conférence, _Louise Grandjonc_, développeur python chez Ulule, nous explique la manière dont nous pouvons optimiser nos requêtes.
Louise nous a expliqué l'importance de **comprendre pourquoi notre filtre est lent**.
Elle nous à expliqué le fonctionnement des INDEX en le comparant avec une table des matières d'une encyclopédie.
Les logs peuvent être trouvés via les commandes suivantes :
    * <code> show log_directory
    * show config_file </code>
  * La fonction EXPLAIN renvoi le plan d’exécution choisi par le query planner




### 13 h 15 : Triggers - Friends To Handle With Care

_Charles Clavadetscher_, DBA Sénior chez KOF, nous a expliqué la manière dont fonctionne les TRIGGERS.
Les Triggers sont un code procédural éxécuté en réponse a certains éventements.
Il est conseillé de donner explicitement a un utilisateur les permission sur les TRIGGERS. La permission sur la modifcation des données alloue automatiquement la permisson sur les TRIGGERS.
Charles nous propose plusieurs recommandation a la création et l’utilisation des TRIGGERS :
  *  En prendre particulièrement soin
  *  Effectuer un babkup avant la mise en production
  *  Tester le fonctionnement
  *  Documenter le comportement



### 14 h 10 : Change Data Capture for a brave new world

_Hannu Valtonner_, Co- fondateur de la société Aiven, nous à parler de la manière dont nous pouvons conserver une trace des changements dans les bases de données.
Hannu nous a parlé des différences entre les moyens utilisés avant ( pg_dump tout les soirs, outils ETL...)
et les possibilités aujourd'hui (Logical decoding, Réplication)
Il nous a expliqué la manière de créer les réplications.

Postgresql.conf :
   * <code>
   * wal_level = logical
   * max_rep_slots = 10
   * max_sender = 10
   * </code>

   * <code>CREATE ROLE foo REPLICATION LOGIN</code>



### 15 h 15 Titre de la conférence : Herd of containers

_Saad DIF_ est Architecte de données chez Bla Bla Car.
Lors de cette conférence, Saad nous expose la manière dont Bla Bla Car utilise PostgreSQL dans des conteneurs.
Il nous explique dans un premier temps les raisons du choix d'un conteneur :
  * Allocation de ressources
  * Rapidité de développement

Il nous dévoile pourquoi Bla Bla Car a choisi Rkt (Rocket) au lieu de Docker.
Un des principes suivi pour mettre en place tout cela : **Connais tes besoins**

Prochaine étape : Docker ? Cloud ?


### 16 h 10 Titre de la conférence : A look at the Elephants trunk - PostgreSQL 11

Magnus Hagander est un membre de la Core Team de PostgreSQL et un commiter. Il est aussi président de PostgreSQL Europe.
Lors de cette conférence, Magnus nous a donné des informations sur les nouveautés à prévoir dans PostgreSQL 11.
Il nous a montré dans quels domaines seront orientés les nouvelles fonctionnalités de PostgreSQL11 :

  * Administration DBA (WAL segment size configurable,
  * SQL (RANGE BETWEEN)
  * Réplication de sauvegarde (backup réplication)
  * Performances (Amélioration du parallélisme, Amélioration Partitionnement)
