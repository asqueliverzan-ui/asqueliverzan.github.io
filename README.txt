AS QUELIVERZAN — SITE V2
==========================

Cette version est une maquette fonctionnelle de portail club, avec :
- identité gris/noir + vrai logo Footeo utilisé comme ressource officielle du club ;
- équipes A D1, B D3, Futsal D1 ;
- matchs et résultats 2026-2027 récupérés depuis les sources publiques consultées ;
- calendrier filtrable ;
- statistiques / historique ;
- partenaires actifs : Popeyes, Intersport, Conseil Départemental du Finistère ;
- administration de démonstration ;
- ajout de joueur ;
- ID permanent ;
- multi-appartenance aux équipes ;
- statut actif / fin de saison / archivé ;
- export/import JSON ;
- architecture prévue pour les synchronisations District / Ligue / Footeo / FFF-FMI.

IMPORTANT — AUTOMATISATION
--------------------------
La V2 ne prétend PAS avoir un accès API public FMI/Footclubs qui n'est pas documenté.
Le site statique ne peut pas, à lui seul, se connecter de manière sécurisée à Footclubs/FMI.
La production doit ajouter un backend + base de données + tâches planifiées.
Le backend pourra :
1. récupérer les données publiques District/Ligue/Footeo ;
2. importer les exports autorisés ;
3. intégrer les données FFF/FMI uniquement via un accès officiellement disponible/autorisé ;
4. normaliser les joueurs avec l'ID interne QEL-xxx ;
5. historiser chaque saison ;
6. publier les changements sur le site.

DONNÉES
-------
Les données incluses correspondent aux informations publiques consultées fin septembre 2026.
Le calendrier complet peut évoluer : la synchronisation serveur devra toujours conserver la date/heure de dernière mise à jour et la source.

LOGO
----
Le logo du site utilise l'asset public du club hébergé par Footeo. Pour un hébergement définitif, il est préférable d'héberger une copie autorisée du fichier dans les assets du site.

SÉCURITÉ
--------
L'administration de cette démo n'est PAS sécurisée : elle utilise localStorage.
Pour une vraie mise en production :
- authentification ;
- rôles (président, secrétaire, coach, etc.) ;
- mots de passe hashés ;
- HTTPS ;
- sauvegardes ;
- journal des modifications ;
- séparation des données publiques et privées ;
- aucune donnée personnelle inutile publiée au public.

PROCHAINE ÉTAPE TECHNIQUE
-------------------------
Créer le backend (par exemple Node/PostgreSQL ou PHP/MySQL), puis brancher les connecteurs.
L'objectif est que l'administrateur ne saisisse manuellement qu'une correction exceptionnelle, tandis que les calendriers/résultats/participations/statistiques proviennent des sources officielles ou des imports autorisés.
