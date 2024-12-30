# Table des matières

1. [Définitions](#définitions)  
2. [Objectifs](#objectifs)  
3. [Sources des données](#sources-des-données)  
4. [Présentation du dépôt](#présentation-du-dépôt)

---

## 1. Définitions

### Performance d’un joueur de football
Nous entendons par **performance** un indicateur agrégé qui évalue les actions d’un joueur lors de la saison, sous divers aspects *(buts marqués, passes décisives, volume de jeu, impact défensif, etc.)*. Cette mesure peut être sous forme de note (ou **rating**) calculée sur la base des données brutes (statistiques de matchs, évaluations experts, etc.) et permet de comparer des joueurs évoluant à différents postes.

### Transfert
Mouvement d’un joueur d’un club à un autre, impliquant parfois un montant financier. Les **transferts** sont souvent considérés comme un indicateur de la valeur potentielle ou actuelle d’un joueur et reflètent l’attractivité de son profil pour de nouvelles équipes.

---

## 2. Objectifs

Notre projet vise à **prédire la performance future** d’un joueur en prenant en compte :

1. Ses **statistiques individuelles** *(buts, passes, tirs, interceptions, etc.)* sur plusieurs saisons.  
2. Les **transferts** effectués *(changement de ligue, d’équipe)*.  
3. Les **données d’équipe** *(classements, performance globale, concurrence au poste)*.

Grâce à cette analyse, nous souhaitons notamment :

- Identifier les facteurs qui influencent la performance d’un joueur lors d’une nouvelle saison.  
- Explorer l’impact qu’a un changement de club ou de championnat sur sa performance.

---

## 3. Sources des données

Nous nous sommes principalement appuyés sur :

- **FBref** : pour les statistiques de match et de performance des joueurs *(buts, passes, minutes jouées, etc.)*.  
- **Transfermarkt** : pour connaître la valeur marchande et l’historique des transferts.  
- **SofaScore** : pour récupérer les notes *(ratings)* attribuées aux joueurs.  
- **Données internes d’équipes** : afin de compléter l’analyse sur la concurrence au poste et le classement de l’équipe.

Les données sont soit **scrapées** directement *(via `requests`, `BeautifulSoup`)*, soit chargées depuis des **APIs publiques** lorsque disponibles. Les fichiers obtenus (pkl, csv…) sont stockés localement dans des dossiers tels que `fbref_data/`, `tm_data/`, `sf_data/`, etc.

---

## 4. Présentation du dépôt

- **`main.ipynb`**   
  - Contenant une version “exécutée” qui présente les résultats et les visualisations *(radars, cartes interactives, courbes de loss, etc.)*, même en cas d’indisponibilité ponctuelle des sources. C’est cette version exécutée qui fait office de **rapport final**.

- **`data/`**  
  - Contient une copie locale de certaines données.

- **`requirements.txt`**  
  - Liste des bibliothèques nécessaires pour le projet *(pandas, numpy, matplotlib, etc.)*.  
  - Il suffit de lancer `pip install -r requirements.txt` au démarrage pour reproduire l’environnement.