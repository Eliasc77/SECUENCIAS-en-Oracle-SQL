# SECUENCIAS-en-Oracle-SQL

#### SECUENCIA
##### es una funcionalidad que se emplea para generar valores enteros secuenciales y q  sean unicos, estos valores seran 
##### asignados a campos numericos y se utilizan para claves primarias o primary keys,
##### LAS SECUENCIAS TRABJAAN UNIDAS A ESTAS RESTRICCIONES PARA GARANTIZAR Q LOS VALORES DE LAS MISMAS NO SE REPITAN
##### ES UNA ESPECIE DE TABLA CON UN CAMPO NUMERICO EN EL CUAL SE ALMACENA UN VALOR Q CADA VEZ Q SE CONSULTA SE INCREMENTA PARA SER REFLEJADO EN LA SGTE CONSULTA
##### Y ASI SUCESIVAMENTE, las secuencias estan compuestas : 

1. NOMBRE SECUENCIA
2. VALOR ENTERO
3. VALOR MAXIMO
4. VALOR MINIMO
5. CICLO

###### existe dos formas de crear secuencia ya sea por codigo o manualmente.

```sql
create table libros(
idlibro int not null primary key,
titulo varchar (40) not null,
autor varchar (40) null,
precio (5,2)
);
```

> crear secuencia 
```sql
create sequence secuencialibros
start with 1
increment by 1
maxvalue 9999
minvalue 1
cycle;
```

##### Primero Iniciamos la Secuencia
```sql
select secuencialibros.nextval from dual;
```

##### procedemos a incertar valores utilizando la secuencia
```sql
insert into libros values (secuencialibros.currval, ' El quijote' , 'Miguel de Cervantes' , 500.00 ) ;
```
|IDLIBRO |  TITULO |  AUTOR | PRECIO |
|------ :|------- :|-------:|-------:|
| 1 | El quijote | Miguel de cervantes | 500 |
