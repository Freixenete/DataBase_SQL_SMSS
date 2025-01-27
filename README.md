# DataBase_SQL_SMSS
Data base first touch with SQL SMSS(SQL Management Server Studio)

##1. One entity


create table professors (
	inicials varchar(5) not null,
	dni varchar(9) not null,
	nom varchar(205) not null,
	email varchar(259) not null,
	data_naixemant date null,
	constraint professors_pk
		primary key (inicials),
	constraint dni_ak
		unique (dni),
	constraint email
		unique (email),
	constraint nom_ak
		unique (nom)
);

Ex from "https://github.com/ctrl-alt-d/BaseDeDades/blob/main/AEA2/MR/traduccio-del-model-entitat-relacio-al-model-relacional.md"

![alt text](https://github.com/Freixenete/DataBase_SQL_SMSS/blob/main/una%20entidad.png "Una entidad")
