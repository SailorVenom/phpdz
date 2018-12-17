# Отладка БД для работы


CREATE SCHEMA dz_db;
 CREATE TABLE users
(
     id int PRIMARY KEY NOT NULL AUTO_INCREMENT,
 email varchar(128) NOT NULL,
     username varchar(64) NOT NULL,
     password varchar(128) NOT NULL,
     admin int DEFAULT 0
 );


CREATE UNIQUE INDEX users_id_uindex ON users (id);


CREATE TABLE posts
 	(
	id int PRIMARY KEY NOT NULL AUTO_INCREMENT,
	image varchar(255),
	description text NOT NULL,
	likes int DEFAULT 0
	);

CREATE UNIQUE INDEX posts_id_uindex ON posts (id);


CREATE TABLE comments
 (
     id int PRIMARY KEY NOT NULL AUTO_INCREMENT,
     post_id int NOT NULL,
    text text NOT NULL,
username varchar(64) NOT NULL,
date datetime NOT NULL
);

CREATE UNIQUE INDEX comments_id_uindex ON comments (id);

 CREATE TABLE cats
 (id int primary key not null auto_increment,
 post_id int not null,
 username_id int not null
     );
