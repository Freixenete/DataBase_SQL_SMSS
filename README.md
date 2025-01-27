# DataBase_SQL_SMSS
Data base first touch with SQL SMSS(SQL Management Server Studio)

## 1. One entity


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


## 2. Two entities with connectors

create table piscinas (
	codigo varchar(4) not null,
	poblacion varchar(250),
	m3 int not null,
	constraint piscinas_pk
		primary key (codigo)
)

create table tratamiento(
	codigo_piscina varchar(4) not null,
	data_hora datetime not null,
	codi_tecnic varchar(2) not null,
	explicacion_tratamiento text,
	constraint tratamiento_pk
		primary key (data_hora, codi_tecnic),
	constraint tratamiento_a_piscina_fk
		foreign key (codigo_piscina)
		references piscinas (codigo)
)

Ex from "https://github.com/ctrl-alt-d/BaseDeDades/blob/main/AEA2/MR/traduccio-del-model-entitat-relacio-al-model-relacional.md"

![alt text](https://github.com/Freixenete/DataBase_SQL_SMSS/blob/main/conexiones.png "Conexiones")
