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

 | nombre            | documento           |   domicilio   |  fechaingreso   |  seccion   |  sueldo  |
 | ------------------|:----------------:|----------------:| ---------:| -----------:| ------------------:|
 | Juan Perez | 22333444 |  Colon 123   | 08/10/1990  | Gerencia | 900.50|
 | Ana Acosta | 23444555 |  Caseros 987   | 18/12/1995  | Secretaria | 590.30|
 | Lucas Duarte | 25666777|  Sucre 235   | 15/05/2005  | Sistemas | 790|
 | Pamela Gonzalez | 26777888 |  Sarmiento 873   | 12/02/1999  | Secretaria | 550| 
 | Marcos Juarez | 30000111 |  Rivadavia 801   | 22/09/2002  | Contaduria | 630.70| 
 | Yolanda perez | 35111222 |  Colon 180   | 08/10/1990  | Administracion | 400|
 | Rodolfo perez | 35555888 |  Coronel Olmedo 588  | 28/05/1990  | Sistemas | 800| 
 
 > Funcions MAX nos retorna el valor maximo q contine un campo especifico de la tabla.
 
