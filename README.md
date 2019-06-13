# SQL Lab No. 1 - June 13th 2019

Just notes from the labs, friend.

## SQL Join

After we create a database with owners and cats...

```SQL
    CREATE TABLE owners (id INTEGER PRIMARY KEY, name TEXT, hunter BOOLEAN, nen TEXT);
```

where the cats belong to owners...

```SQL
CREATE TABLE cats (
id INTEGER PRIMARY KEY,
name TEXT,
age INTEGER,
breed TEXT,
mood TEXT,
owner_id INTEGER);
```

And add some items to each table...

```SQL
    INSERT INTO owners (name, hunter, nen)
    VALUES ("Gon", 1, "Enhancing"),
          ("Hisoka", 0, "Transmutation"),
          ("Old Woman", 0, "none");

    INSERT INTO cats (name, age, breed, mood, owner_id)
    VALUES   ("Maru", 3, "Scottish Fold", "happy", 1),
            ("Hana", 3, "Tabby", "hungry", 1),
            ("Nona", 4, "Tortoiseshell", "jolly", 2);

    INSERT INTO cats (name, age, breed, mood)
    VALUES ("Lil' Bub", 2, "perma-kitten", "scratchy"),
          ("Cat in the Hat", 20, "abnormally anthropomorphic", "sketchy");
```

We can use an inner join to get the names and breeds of the cats, as well as their owner's names:

```SQL
    SELECT cats.name, cats.breed, owners.name AS "owner_name" FROM cats INNER JOIN owners ON cats.owner_id = owners.id;
```
