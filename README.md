# DataBase_SQL_SMSS
Data base first touch with SQL SMSS(SQL Management Server Studio)

## 1. One entity


create table professors ( <br>
	inicials varchar(5) not null, <br>
	dni varchar(9) not null, <br>
	nom varchar(205) not null, <br>
	email varchar(259) not null, <br>
	data_naixemant date null, <br>
	constraint professors_pk <br>
		primary key (inicials), <br>
	constraint dni_ak <br>
		unique (dni), <br>
	constraint email <br>
		unique (email), <br>
	constraint nom_ak <br>
		unique (nom) <br>
);

Ex from "https://github.com/ctrl-alt-d/BaseDeDades/blob/main/AEA2/MR/traduccio-del-model-entitat-relacio-al-model-relacional.md"

![alt text](https://github.com/Freixenete/DataBase_SQL_SMSS/blob/main/una%20entidad.png "Una entidad")


## 2. Two entities with connectors

create table piscinas ( <br>
	codigo varchar(4) not null, <br>
	poblacion varchar(250), <br>
	m3 int not null, <br>
	constraint piscinas_pk <br>
		primary key (codigo) <br>
)

create table tratamiento( <br>
	codigo_piscina varchar(4) not null, <br>
	data_hora datetime not null, <br>
	codi_tecnic varchar(2) not null, <br>
	explicacion_tratamiento text, <br>
	constraint tratamiento_pk <br>
		primary key (data_hora, codi_tecnic), <br>
	constraint tratamiento_a_piscina_fk <br>
		foreign key (codigo_piscina) <br>
		references piscinas (codigo) <br>
)

Ex from "https://github.com/ctrl-alt-d/BaseDeDades/blob/main/AEA2/MR/traduccio-del-model-entitat-relacio-al-model-relacional.md"

![alt text](https://github.com/Freixenete/DataBase_SQL_SMSS/blob/main/conexiones.png "Conexiones")
