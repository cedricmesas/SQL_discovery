# Blogging

**USERS database**

| id_users | name | 
| :-: | :-: |
| 1 | name_01 |
| 2 | name_02 |
| 3 | name_03 |


**ARTICLE database**

| id_article | body | id_user
| :-: | :-: | :-: |
| 1 | body_01 | 1 |
| 2 | body_02 | 3 |
| 3 | body_03 | 2 |

**CATEGORY database**

| id_category | title | id_article
| :-: | :-: | :-: |
| 1 | ton_title_01 | 1 |
| 2 | ton_title_02 | 3 |
| 3 | ton_title_03 | 2 |

**TAG database**

| id | title | color |id_category
| :-: | :-: | :-: |:-: |
| 1 | title_01 | color_01 | id_category_01 |
| 2 | title_02 | color_02 | id_category_02 |
| 3 | title_03 | color_03 | id_category_03 |

# MOOCAcademy

**USERS database**

| id | first_name | last_name | age |
| :-: | :-: | :-: | :-: |
| 1 | Claude | Monnaie | 34
| 2 | Robert | Hutte | 67
| 3 | Manu | Micro | 50

```ruby 
CREATE TABLE 'users' (
    'id' INTEGER PRIMARY KEY AUTOINCREMENT NOT NULL,
    'first_name' NVARCHAR(60), 
    'last_name' NVARCHAR(60),
    'age' INTEGER
);
```

**COURS database**

| id | title| description |
| :-: | :-: | :-: |
| 1 | ton_cours_1 | le_title_1 |
| 2 | ton_cours_1 | le_title_2 |
| 3 | ton_cours_3 | le_title_3 |

```ruby 
CREATE TABLE 'cours' (
    'id' INTEGER PRIMARY KEY AUTOINCREMENT NOT NULL,
    'title' NVARCHAR(180) NOT NULL, 
    'description' TEXT
);
```

**LESSONS database**

| id | title| body | id_cours |
| :-: | :-: | :-: | :-: |
| 1 | Title_01 | body_01 | id_cours01 |
| 2 | Title_02 | body_02 | id_cours02 |
| 3 | Title_03 | body_03 | id_cours03 |

```ruby
CREATE TABLE 'lessons' (
    'id' INTEGER PRIMARY KEY AUTOINCREMENT,
    'title' NVARCHAR(120) NOT NULL, 
    'body' TEXT,
    id_cours INTEGER NOT NULL,
    FOREIGN KEY (id_cours) REFERENCES cours(id)
);
```

# THE HACKING PINS

**USERS database**

| id | first_name | last_name | age |
| :-: | :-: | :-: | :-: |
| 1  | Claude | Monnaie | 34
| 2 | Robert | Hutte | 67
| 3 | Manu | Micro | 50


```ruby
CREATE TABLE 'users' (
    'id' INTEGER PRIMARY KEY AUTOINCREMENT,
    'first_name' NVARCHAR(60) NOT NULL, 
    'last_name' NVARCHAR(60),
    'age' INTEGER
);
```

**PINS database**

| id | url_pictures | title | description | id_users |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| 1 | www.ton_url_pins1 | title_pins1 | description_pins1 | id_users_01
| 2 | www.ton_url_pins2 | title_pins2 | description_pins2 | id_users_02
| 3 | www.ton_url_pins3 | title_pins3 | description_pins3 | id_users_03


```ruby
CREATE TABLE 'pins' (
    'id' INTEGER PRIMARY KEY AUTOINCREMENT,
    'url_pictures' TEXT NOT NULL, 
    'title' NVARCHAR(240),
    'description' TEXT,
    id_users INTEGER NOT NULL,
    FOREIGN KEY (id_users) REFERENCES users('id')
);
```

**COMMENTS database**

| id | comments | id_pins | id_users |
| :-: | :-: | :-: | :-: |
| 1 | ton_comments_1 | id_pins_01 | id_users_01
| 2 | ton_comments_2 | id_pins_02 | id_users_02
| 3 | ton_comments_3 | id_pins_03 | id_users_03

```ruby
CREATE TABLE 'comments' (
    'id' INTEGER PRIMARY KEY AUTOINCREMENT,
    'comments' TEXT,
    id_pins INTEGER NOT NULL,
    id_users INTEGER NOT NULL,
    FOREIGN KEY (id_pins) REFERENCES pins(id), 
    FOREIGN KEY (id_users) REFERENCES users('id')
);
```

# THE HACKING NEWS

**USERS database**

| id | first_name | last_name |
| :-: | :-: | :-: |
| 1 | first_name_01 | last_name_01 |
| 2 | first_name_02 | last_name_02 |
| 3 | first_name_03 | last_name_03 |

```ruby
CREATE TABLE 'users' (
    'id' INTEGER PRIMARY KEY AUTOINCREMENT,
    'first_name' NVARCHAR(60),
    'last_name' NVARCHAR(60) 
);
```

**COMMENTS database**

| id | comments | id_users | id_links | id_comments |
| :-: | :-: | :-: | :-: | :-: |
| 1 | ton_comments_1 | id_users_01 | id_links_01 | id_comments_01 |
| 2 | ton_comments_2 | id_users_02 | id_links_02 | id_comments_02 |
| 3 | ton_comments_3 | id_users_03 | id_links_03 | id_comments_03 |

```ruby
CREATE TABLE 'comments' (
    'id' INTEGER PRIMARY KEY AUTOINCREMENT,
    'comments' TEXT,
    id_users INTEGER NOT NULL,
    id_links INTEGER NOT NULL,
    id_comments INTEGER NOT NULL,
    FOREIGN KEY (id_users) REFERENCES users('id')
    FOREIGN KEY (id_links) REFERENCES links('id')
    FOREIGN KEY (id_comments) REFERENCES comments('id')
);
```

**LINKS database**

| id | links_url | links_text | id_users |
| :-: | :-: | :-: | :-: |
| 1 | links_url_01 | links_text_01 | id_users_01 |
| 2 | links_url_02 | links_text_02 | id_users_02 |
| 3 | links_url_03 | links_text_03 | id_users_03 |

```ruby
CREATE TABLE 'links' (
    'id' INTEGER PRIMARY KEY AUTOINCREMENT,
    'links_url' TEXT,
    'links_text' NVARCHAR(240),
    id_users INTEGER NOT NULL,
    FOREIGN KEY (id_users) REFERENCES users('id')
);
```


# THE HACKING CLASS

**STUDENTS database**

| id | name | email | id_courses |
| :-: | :-: | :-: | :-: |
| 1 | name_01 | email@name1 | id_courses_01 |
| 2 | name_02 | email@name2 | id_courses_02 |
| 3 | name_03 | email@name3 | id_courses_03 |

```ruby
CREATE TABLE 'students' (
    'id' INTEGER PRIMARY KEY AUTOINCREMENT,
    'name' NVARCHAR(60),
    'email' NVARCHAR(240),
    id_courses INTEGER NOT NULL,
    FOREIGN KEY (id_courses) REFERENCES courses('id')
);
```

**COURSES database**

| id | name_courses |
| :-: | :-: |
| id_courses_01 | name_courses_01 |
| id_courses_02 | name_courses_02 |
| id_courses_03 | name_courses_03 |

```ruby
CREATE TABLE 'courses' (
    'id' INTEGER PRIMARY KEY AUTOINCREMENT,
    'name_courses' NVARCHAR(240)
);
```