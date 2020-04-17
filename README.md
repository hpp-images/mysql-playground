# MySQL playground

Easy instant MySQL image for a coding test, classes, just playground, etc.
You can use characters of utf-8, so you can input Japanese.

## how to use

0. install **`docker`**
1. run `docker run -d --name playground -p 3306:3306 hpprc/mysql_playground`
2. run `docker exec -it playground mysql -uroot -proot`


## how to enter the container

```bash
docker exec -i -t playground bash
```

you can enter mysql to do this.

```bash
# inside container

mysql -uroot -proot
```

sample queries.

```sql

show databases;

# result
#
# +--------------------+
# | Database           |
# +--------------------+
# | information_schema |
# | mysql              |
# | performance_schema |
# | play               |
# | sys                |
# +--------------------+

use play;

show tables;

# result
#
# Empty set (0.00 sec)

```

## Customize

You can add any SQL queries in init directory.

### example

```sql
CREATE TABLE `供給` (
  `部門番号` int(11) NOT NULL,
  `部品番号` int(11) NOT NULL,
  `業者番号` int(11) NOT NULL,
  `単価` int(11) NOT NULL,
  `数量` int(11) NOT NULL
) ENGINE=InnoDB;

INSERT INTO `供給` (`部門番号`, `部品番号`, `業者番号`, `単価`, `数量`) VALUES
(1, 1, 1, 25000, 1000),
(1, 1, 2, 26000, 200),
(2, 1, 1, 24980, 800),
(3, 1, 1, 25000, 2000),
(3, 2, 3, 820, 200),
(3, 4, 3, 5100, 2000);
```


## how to enter the mysql in docker container directly

```
docker exec -i -t playground mysql -uroot -proot
```

