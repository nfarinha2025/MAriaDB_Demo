# MAriaDB_Demo



# Part A

```sql
MariaDB [mysql]> select * from user where user='admin' and host='localhost'\G
*************************** 1. row ***************************
                  Host: localhost
                  User: admin
              Password: *D821809F681A40A6E379B50D0463EFAE20BDD122
           Select_priv: N
           Insert_priv: N
           Update_priv: N
           Delete_priv: N
           Create_priv: N
             Drop_priv: N
           Reload_priv: N
         Shutdown_priv: N
          Process_priv: N
             File_priv: N
            Grant_priv: N
       References_priv: N
            Index_priv: N
            Alter_priv: N
          Show_db_priv: N
            Super_priv: N
 Create_tmp_table_priv: N
      Lock_tables_priv: N
          Execute_priv: N
       Repl_slave_priv: N
      Repl_client_priv: N
      Create_view_priv: N
        Show_view_priv: N
   Create_routine_priv: N
    Alter_routine_priv: N
      Create_user_priv: N
            Event_priv: N
          Trigger_priv: N
Create_tablespace_priv: N
   Delete_history_priv: N
              ssl_type: 
            ssl_cipher: 
           x509_issuer: 
          x509_subject: 
         max_questions: 0
           max_updates: 0
       max_connections: 0
  max_user_connections: 0
                plugin: mysql_native_password
 authentication_string: *D821809F681A40A6E379B50D0463EFAE20BDD122
      password_expired: N
               is_role: N
          default_role: 
    max_statement_time: 0.000000
1 row in set (0.004 sec)

MariaDB [mysql]> select * from db   where user='admin' and host='localhost'\G
*************************** 1. row ***************************
                    Host: localhost
                      Db: lyric
                    User: admin
             Select_priv: Y
             Insert_priv: Y
             Update_priv: Y
             Delete_priv: Y
             Create_priv: Y
               Drop_priv: Y
              Grant_priv: N
         References_priv: Y
              Index_priv: Y
              Alter_priv: Y
   Create_tmp_table_priv: Y
        Lock_tables_priv: Y
        Create_view_priv: Y
          Show_view_priv: Y
     Create_routine_priv: Y
      Alter_routine_priv: Y
            Execute_priv: Y
              Event_priv: Y
            Trigger_priv: Y
     Delete_history_priv: Y
Show_create_routine_priv: Y
1 row in set (0.003 sec)





# Part B
```sql

MariaDB [mysql]> select * from tables_priv where user='sales'\G
*************************** 1. row ***************************
       Host: localhost
         Db: lyric
       User: sales
 Table_name: artists
    Grantor: nate@localhost
  Timestamp: 0000-00-00 00:00:00
 Table_priv: Select,Insert,Update
Column_priv: 
*************************** 2. row ***************************
       Host: localhost
         Db: lyric
       User: sales
 Table_name: members
    Grantor: nate@localhost
  Timestamp: 0000-00-00 00:00:00
 Table_priv: Select,Insert,Update
Column_priv: 
*************************** 3. row ***************************
       Host: localhost
         Db: lyric
       User: sales
 Table_name: xrefartistsmembers
    Grantor: nate@localhost
  Timestamp: 0000-00-00 00:00:00
 Table_priv: Select,Insert,Update
Column_priv: 
3 rows in set (0.004 sec)

#Part C
```sql
MariaDB [mysql]> select * from columns_priv where user='artist' and host='localhost';
+-----------+-------+--------+------------+-------------+---------------------+-------------+
| Host      | Db    | User   | Table_name | Column_name | Timestamp           | Column_priv |
+-----------+-------+--------+------------+-------------+---------------------+-------------+
| localhost | lyric | artist | artists    | ArtistID    | 0000-00-00 00:00:00 | Select      |
| localhost | lyric | artist | artists    | ArtistName  | 0000-00-00 00:00:00 | Select      |
| localhost | lyric | artist | artists    | City        | 0000-00-00 00:00:00 | Select      |
| localhost | lyric | artist | artists    | Country     | 0000-00-00 00:00:00 | Select      |
| localhost | lyric | artist | artists    | Region      | 0000-00-00 00:00:00 | Select      |
| localhost | lyric | artist | artists    | WebAddress  | 0000-00-00 00:00:00 | Select      |
+-----------+-------+--------+------------+-------------+---------------------+-------------+
6 rows in set (0.001 sec)

MariaDB [mysql]> select * from tables_priv   where user='artist' and host='localhost';
+-----------+-------+--------+------------+----------------+---------------------+------------+-------------+
| Host      | Db    | User   | Table_name | Grantor        | Timestamp           | Table_priv | Column_priv |
+-----------+-------+--------+------------+----------------+---------------------+------------+-------------+
| localhost | lyric | artist | artists    | nate@localhost | 0000-00-00 00:00:00 |            | Select      |
+-----------+-------+--------+------------+----------------+---------------------+------------+-------------+



#Part D
```sql

MariaDB [lyric]> desc cd;
+------------+-------------+------+-----+---------+-------+
| Field      | Type        | Null | Key | Default | Extra |
+------------+-------------+------+-----+---------+-------+
| ArtistName | varchar(50) | NO   |     | NULL    |       |
| Title      | varchar(50) | YES  |     | NULL    |       |
| TrackNum   | smallint(6) | NO   |     | NULL    |       |
| TrackTitle | varchar(50) | YES  |     | NULL    |       |
+------------+-------------+------+-----+---------+-------+


MariaDB [lyric]> SELECT * FROM cd;
+---------------+--------------------+----------+--------------------------------+
| ArtistName    | Title              | TrackNum | TrackTitle                     |
+---------------+--------------------+----------+--------------------------------+
| The Bullets   | Time Flies         |        1 | Bob's Dream                    |
| The Bullets   | Time Flies         |        3 | Third's Folly                  |
| The Bullets   | Time Flies         |        2 | My Wizard                      |
| Confused      | Smell the Glove    |        1 | Fat Cheeks                     |
| The Neurotics | Meet the Neurotics |        1 | Hottie                         |
| The Neurotics | Meet the Neurotics |        2 | Goodtime March                 |
| The Neurotics | Meet the Neurotics |        3 | TV Day                         |
| The Neurotics | Meet the Neurotics |        4 | Call Me an Idiot               |
| The Neurotics | Meet the Neurotics |        5 | 25                             |
| The Neurotics | Meet the Neurotics |        6 | Palm                           |
| The Neurotics | Meet the Neurotics |        7 | Front Door                     |
| The Neurotics | Meet the Neurotics |        8 | Where's the Rain               |
| Confused      | Smell the Glove    |        2 | Rocky and Natasha              |
| Confused      | Smell the Glove    |        3 | Dweeb                          |
| Confused      | Smell the Glove    |        4 | Funky Town                     |
| Confused      | Smell the Glove    |        5 | Shoes                          |
| Confused      | Smell the Glove    |        6 | Time In - In Time              |
| Sonata        | Sonatas            |        1 | Violin Sonata No. 1 in D Major |
| Sonata        | Sonatas            |        2 | Violin Sonata No. 2 in A Major |
| Sonata        | Sonatas            |        3 | Violin Sonata No. 4 in E Minor |
| Sonata        | Sonatas            |        4 | Piano Sonata No. 1             |
| Sonata        | Sonatas            |        5 | Clarinet Sonata in E Flat      |
| The Neurotics | Neurotic Sequel    |        1 | Song 1                         |
| The Neurotics | Neurotic Sequel    |        2 | Song 2                         |
| The Neurotics | Neurotic Sequel    |        3 | Song 3                         |
| The Neurotics | Neurotic Sequel    |        4 | Song 4                         |
| The Neurotics | Neurotic Sequel    |        5 | Song 5                         |
| The Neurotics | Neurotic Sequel    |        6 | Song 6                         |
| The Neurotics | Neurotic Sequel    |        7 | Song 7                         |
| The Neurotics | Neurotic Sequel    |        8 | Song 8                         |
| The Neurotics | Neurotic Sequel    |        9 | Song 8 and 1/2                 |
| Louis Holiday | Louis at the Keys  |        1 | I Don't Know                   |
| Louis Holiday | Louis at the Keys  |        2 | What's the Day                 |
| Louis Holiday | Louis at the Keys  |        3 | Sirius                         |
| Louis Holiday | Louis at the Keys  |        4 | Hamburger Blues                |
| Louis Holiday | Louis at the Keys  |        5 | Road Trip                      |
| Louis Holiday | Louis at the Keys  |        6 | Meeting You                    |
| Louis Holiday | Louis at the Keys  |        7 | Improv 34                      |
| Louis Holiday | Louis at the Keys  |        8 | Hey                            |
| The Bullets   | Time Flies         |        4 | Leather                        |
| The Bullets   | Time Flies         |        5 | Hot Cars Cool Nights           |
| The Bullets   | Time Flies         |        6 | Music in You                   |
| The Bullets   | Time Flies         |        7 | Don't Care About Time          |
| The Bullets   | Time Flies         |        8 | Kiss                           |
| The Bullets   | Time Flies         |        9 | Pizza Box                      |
| The Bullets   | Time Flies         |       10 | Goodbye                        |
| Confused      | Smell the Glove    |        7 | Wooden Man                     |
| Confused      | Smell the Glove    |        8 | UPS                            |
| Confused      | Smell the Glove    |        9 | Empty                          |
| Confused      | Smell the Glove    |       10 | Burrito                        |
+---------------+--------------------+----------+--------------------------------+


#PArt E
```sql
MariaDB [mysql]> SELECT user, host, password FROM user;
+-------------+-----------------------------+-------------------------------------------+
| User        | Host                        | Password                                  |
+-------------+-----------------------------+-------------------------------------------+
| mariadb.sys | localhost                   |                                           |
| root        | localhost                   | *914A43D8AD476F341C2DA23177528726E4D1ED0F |
| nate        | localhost                   | invalid                                   |
| PUBLIC      |                             |                                           |
|             | localhost                   |                                           |
|             | nathans-macbook-air-2.local |                                           |
| admin       | localhost                   | *D821809F681A40A6E379B50D0463EFAE20BDD122 |
| sales       | localhost                   | *D821809F681A40A6E379B50D0463EFAE20BDD122 |
| artist      | localhost                   | *D821809F681A40A6E379B50D0463EFAE20BDD122 |
+-------------+-----------------------------+-------------------------------------------+



