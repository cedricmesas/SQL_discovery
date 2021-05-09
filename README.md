Pour lire ce repo, il te faut :

- installer SQLite
- télécharger DB Browser for SQLite


Les exercices : 

Dans le fichier **bdd.md** tu trouveras :

### Architecture des tables, attributs et jointures sous forme de tableau. 

_Par exemple_ :

**USERS database**

| id_users | name | 
| :-: | :-: |
| 1 | name_01 |
| 2 | name_02 |
| 3 | name_03 |

### Les commandes de création 

_Par exemple_:

```sql
CREATE TABLE 'users' (
    'id' INTEGER PRIMARY KEY AUTOINCREMENT,
    'name' NVARCHAR(60) NOT NULL
);
```

### Les bases de données en vrai via SQLite3. 

Ce sont les dossiers intitulés : 
- **blogging**
- **moocacademy**
- **the_hacking_class**
- **the_hacking_news**
- **the_hacking_pins**

### Les requêtes sur le fichier "chinook.db"

A partir du fichier "chinook.db", effectuer les requêtes demandées dans le fichier "bdd.md". 

_Par exemple_: 

1. Récupérer **tous les albums**

```sql
SELECT * FROM albums;
```