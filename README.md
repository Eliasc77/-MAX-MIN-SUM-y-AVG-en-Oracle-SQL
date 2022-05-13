# -MAX-MIN-SUM-y-AVG-en-Oracle-SQL
#### estas funciones nos permiten contar registros, calcular sumas, promedios y obtener valores maximos y minimos

```sql
 create table empleados(
  nombre varchar2(30),
  documento char(8),
  domicilio varchar2(30),
  seccion varchar2(20),
  sueldo number(6,2),
  cantidadhijos number(2),
  fechaingreso date,
  primary key(documento)
 );


 insert into empleados
  values('Juan Perez','22333444','Colon 123','Gerencia',5000,2,to_date('10/10/1980','dd/mm/yyyy'));
 insert into empleados
  values('Ana Acosta','23444555','Caseros 987','Secretaria',2000,0,to_date('15/08/1998','dd/mm/yyyy'));
 insert into empleados
  values('Lucas Duarte','25666777','Sucre 235','Sistemas',4000,1,null);
 insert into empleados
  values('Pamela Gonzalez','26777888','Sarmiento 873','Secretaria',2200,3,null);
 insert into empleados
  values('Marcos Juarez','30000111','Rivadavia 801','Contaduria',3000,0,to_date('26/08/2000','dd/mm/yyyy'));
 insert into empleados
  values('Yolanda Perez','35111222','Colon 180','Administracion',3200,1,to_date('25/09/2001','dd/mm/yyyy'));
 insert into empleados
  values('Rodolfo Perez','35555888','Coronel Olmedo 588','Sistemas',4000,3,null);
 insert into empleados
  values('Martina Rodriguez','30141414','Sarmiento 1234','Administracion',3800,4,to_date('14/12/2000','dd/mm/yyyy'));
 insert into empleados
  values('Andres Costa','28444555',default,'Secretaria',null,null,to_date('08/08/1990','dd/mm/yyyy'));
  ```
  
    
    >select * from empleados

 | nombre            | documento           |   domicilio   |  fechaingreso   |  seccion   |  sueldo  |  Cantidad  |
 | ------------------|:----------------:|----------------:| ---------:| -----------:| ------------------:| --------:|
 | Juan Perez | 22333444 |  Colon 123   | 10/10/1980 | Gerencia | 5000| 2|
 | Ana Acosta | 23444555 |  Caseros 987   | 15/08/1998 | Secretaria | 2000|0|
 | Lucas Duarte | 25666777|  Sucre 235   | (null)  | Sistemas | 4000|1|
 | Pamela Gonzalez | 26777888 |  Sarmiento 873   | (null)  | Secretaria | 2200| 3|
 | Marcos Juarez | 30000111 |  Rivadavia 801   | 26/08/2000  | Contaduria | 3000| 0|
 | Yolanda perez | 35111222 |  Colon 180   | 25/09/2001  | Administracion | 3200| 1 | 
 | Rodolfo perez | 35555888 |  Coronel Olmedo 588  | (null) | Sistemas | 4000| 3 |
 | Martina Rodriguez | 30141414 |  Sarmiento 1234  | 14/12/2000  | Administracion | 3800| 4|
 | Andres Costa | 28444555 |  (null) | 08/08/1990  | Secretaria | (null)| (null)|
 
 ___
 > Funcions MAX nos retorna el valor maximo q contine un campo especifico de la tabla.

```sql
select MAX(sueldo) as "Mayor Sueldo" from empleados;
```

|Mayor Sueld |
|--------- : |
|5000|

___
>Funcion Min nos retorna el valor minimo q contine un campo especifico de la tabla
|Menor Sueldo|
|--------- : |
|2000|

___

```sql
select MAX(sueldo) as "Mayor Sueldo", MIN (sueldo) as "Menor Sueldo" from empleados;
```
| Mayor Sueld | Menor Sueldo |
| :--------- :|:--------- :|
| 5000 | 2000 |

___
```sql
SELECT  max(cantidadhijos) as hijos
FROM EMPLEADOS
WHERE nombre like '%Perez%';
```

|Hijos|
|----:|
|3|
___

```sql
SELECT  min(cantidadhijos) as hijos
FROM EMPLEADOS
WHERE nombre like '%Perez%';
```

|Hijos|
|----:|
|1|

___

>Funcion AVG, se encarga de calcular el promedio de los registros insertados en una tabla
```sql
select avg(sueldo) as "Promedio Sueldos" from empleados
```
|Promedio Sueldos|
|----:|
|3400|


```SQL
select avg(sueldo) as "Promedio Secretarias" from empleados
where seccion = 'Secretaria';
```

|Promedio Secretarias|
|----:|
|2100|

___
> SUM realiza la sumatoria de todo los registros de un campó en especifico

```SQL
select sum(sueldo) as "Sumatoria de salarios" from empleados;
```
|Sumatoria de salarios|
|----:|
|27200|


```sql
select sum(sueldo) as "Sumatoria de salarios" from empleados
where seccion = 'Sistemas';
```
|Sumatoria de salarios|
|----:|
|8000|

___

> MAX Y MIN tambien operan sobre tipo de datos fecha

```sql
select max(fechaingreso) as "Empleado mas nuevo" , min(fechaingreso) as "Empleado mas Viejo "from empleados;
```

| Empleado mas nuevo | Empleado mas Viejoo|
| --------- :| --------- :|
| 25/09/2001 | 10/10/1980 |
