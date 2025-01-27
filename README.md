# DataBase_SQL_SMSS
Data base first touch with SQL SMSS(SQL Management Server Studio)

## 1. One entity


create table professors ( <br>
&nbsp 	inicials varchar(5) not null, <br>
&nbsp 	dni varchar(9) not null, <br>
&nbsp 	nom varchar(205) not null, <br>
&nbsp 	email varchar(259) not null, <br>
&nbsp 	data_naixemant date null, <br>
&nbsp 	constraint professors_pk <br>
&ensp		primary key (inicials), <br>
&nbsp 	constraint dni_ak <br>
&ensp		unique (dni), <br>
&nbsp 	constraint email <br>
&ensp		unique (email), <br>
&nbsp 	constraint nom_ak <br>
&ensp		unique (nom) <br>
);

Ex from "https://github.com/ctrl-alt-d/BaseDeDades/blob/main/AEA2/MR/traduccio-del-model-entitat-relacio-al-model-relacional.md"

![alt text](https://github.com/Freixenete/DataBase_SQL_SMSS/blob/main/una%20entidad.png "Una entidad")


## 2. Two entities with connectors

create table piscinas ( <br>
&nbsp 	codigo varchar(4) not null, <br>
&nbsp 	poblacion varchar(250), <br>
&nbsp 	m3 int not null, <br>
&nbsp 	constraint piscinas_pk <br>
&ensp		primary key (codigo) <br>
)

create table tratamiento( <br>
&nbsp 	codigo_piscina varchar(4) not null, <br>
&nbsp 	data_hora datetime not null, <br>
&nbsp 	codi_tecnic varchar(2) not null, <br>
&nbsp 	explicacion_tratamiento text, <br>
&nbsp 	constraint tratamiento_pk <br>
&ensp		primary key (data_hora, codi_tecnic), <br>
&nbsp 	constraint tratamiento_a_piscina_fk <br>
&ensp		foreign key (codigo_piscina) <br>
&ensp		references piscinas (codigo) <br>
)

Ex from "https://github.com/ctrl-alt-d/BaseDeDades/blob/main/AEA2/MR/traduccio-del-model-entitat-relacio-al-model-relacional.md"

![alt text](https://github.com/Freixenete/DataBase_SQL_SMSS/blob/main/conexiones.png "Conexiones")
