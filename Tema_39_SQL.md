
# Tema 39: Lenguajes para la definición y manipulación de datos en sistemas de base de datos relacionales. Tipos. Características. Lenguaje SQL.

## ÍNDICE
1. INTRODUCCIÓN  
2. TIPOS DE LENGUAJES EN SISTEMAS DE BASES DE DATOS RELACIONALES  
3. LENGUAJE DE DEFINICIÓN DE DATOS (DDL)  
4. LENGUAJE DE MANIPULACIÓN DE DATOS (DML)  
5. CARACTERÍSTICAS DE LOS LENGUAJES DDL Y DML  
6. LENGUAJE SQL  
    6.1. Ejemplos de DDL en SQL  
    6.2. Ejemplos de DML en SQL  
7. DICCIONARIO DE DATOS  
8. TENDENCIAS ACTUALES  
9. VINCULACIÓN CON EL CURRÍCULO  
10. CONCLUSIÓN  
11. BIBLIOGRAFÍA  

## 1. INTRODUCCIÓN

En la era digital, las bases de datos resultan esenciales para gestionar grandes volúmenes de información en aplicaciones cotidianas como registros web, compras online o reservas.  
Antes de la aparición de los sistemas gestores de bases de datos (SGBD), los sistemas de archivos requerían modificar todos los programas ante cualquier cambio estructural en los datos.  
Para superar esta limitación surgieron los SGBD, que separan los datos de las aplicaciones y han transformado el modo de almacenar, consultar y compartir datos.  

Según Korth y Silberschatz, en *Fundamentos de bases de datos*, comprender su funcionamiento es esencial para diseñar soluciones eficaces de almacenamiento, análisis y procesamiento de datos. Este conocimiento resulta imprescindible tanto en el entorno académico como en el profesional.

Este tema se centra en el estudio de los lenguajes para la definición y manipulación de datos en sistemas de bases de datos relacionales. Se analizarán sus tipos, características principales, y el papel del lenguaje SQL como estándar.  
En la actualidad, estos lenguajes son claves en entornos de IA, big data y computación en la nube, impulsando sistemas más escalables, seguros y adaptados al análisis masivo de datos.

## 2. TIPOS DE LENGUAJES EN SISTEMAS DE BASES DE DATOS RELACIONALES

En los SGBD se utilizan diferentes tipos de lenguajes para interactuar con los datos. Los principales son:

- **Lenguaje de Definición de Datos (DDL)**: define las estructuras de almacenamiento (tablas, índices, vistas).  
- **Lenguaje de Manipulación de Datos (DML)**: permite consultar, insertar, actualizar y eliminar datos.  
- **Lenguaje de Control de Datos (DCL)**: gestiona permisos y control de acceso.  
- **Lenguaje de Control de Transacciones (TCL)**: garantiza la coherencia de los datos mediante la gestión de transacciones.

En este tema nos centraremos en los dos primeros: DDL y DML, que son los más directamente relacionados con la creación y manipulación de datos.

## 3. LENGUAJE DE DEFINICIÓN DE DATOS (DDL)

El DDL se utiliza para definir las estructuras de la base de datos. Incluye comandos como:

- `CREATE`: crea bases de datos, tablas, vistas o índices.  
- `ALTER`: modifica estructuras existentes.  
- `DROP`: elimina estructuras.  
- `TRUNCATE`: borra datos de una tabla manteniendo su estructura.

Estas operaciones afectan directamente al diseño lógico y físico de la base de datos.  
Por ejemplo, para crear una tabla de empleados:

```sql
CREATE TABLE empleados (
    id INT PRIMARY KEY,
    nombre VARCHAR(100),
    salario DECIMAL(10,2)
);
```

## 4. LENGUAJE DE MANIPULACIÓN DE DATOS (DML)

El DML permite gestionar la información contenida en las tablas de la base de datos. Los comandos más habituales son:

- `SELECT`: consulta de datos.  
- `INSERT`: inserción de registros.  
- `UPDATE`: actualización de registros.  
- `DELETE`: eliminación de registros.

Ejemplo básico de consulta:

```sql
SELECT nombre, salario FROM empleados WHERE salario > 2000;
```

## 5. CARACTERÍSTICAS DE LOS LENGUAJES DDL Y DML

- **Simplicidad**: sintaxis declarativa que permite especificar qué se desea obtener.  
- **Formalidad**: basada en fundamentos matemáticos como el álgebra relacional.  
- **Estándar**: basada en SQL, soportada por la mayoría de los SGBD.  
- **Dependencia del SGBD**: algunos comandos avanzados pueden variar según el sistema (MySQL, PostgreSQL, Oracle...)

## 6. LENGUAJE SQL

El SQL (Structured Query Language) es el estándar más ampliamente utilizado en bases de datos relacionales.  
Permite definir estructuras (DDL), manipular datos (DML), gestionar permisos (DCL) y controlar transacciones (TCL).

Su carácter declarativo permite expresar de forma sencilla las operaciones que se desean realizar, sin necesidad de detallar el proceso.

### 6.1. Ejemplos de DDL en SQL

Crear una base de datos:

```sql
CREATE DATABASE empresa;
```

Crear una tabla:

```sql
CREATE TABLE productos (
    id INT PRIMARY KEY,
    nombre VARCHAR(50),
    precio DECIMAL(8,2),
    stock INT
);
```

Modificar una tabla:

```sql
ALTER TABLE productos ADD COLUMN descripcion VARCHAR(255);
```

Eliminar una tabla:

```sql
DROP TABLE productos;
```

### 6.2. Ejemplos de DML en SQL

Insertar datos:

```sql
INSERT INTO productos (id, nombre, precio, stock) VALUES (1, 'Teclado', 29.95, 100);
```

Consultar datos:

```sql
SELECT nombre, precio FROM productos WHERE stock > 50;
```

Actualizar datos:

```sql
UPDATE productos SET precio = 25.00 WHERE id = 1;
```

Eliminar datos:

```sql
DELETE FROM productos WHERE id = 1;
```

## 7. DICCIONARIO DE DATOS

El diccionario de datos es un repositorio que describe los elementos de la base de datos: tablas, vistas, índices, restricciones y relaciones.  
Contiene también los metadatos (datos sobre los datos) necesarios para:

- Documentar el diseño de la base de datos.  
- Garantizar la integridad y la seguridad.  
- Optimizar el rendimiento mediante la gestión de índices y claves.

## 8. TENDENCIAS ACTUALES

En la actualidad, los lenguajes de bases de datos evolucionan hacia:

- **Integración con IA**: automatización en el diseño de consultas y optimización de índices.  
- **Big Data**: integración de SQL con entornos Hadoop y Spark.  
- **Bases NoSQL híbridas**: sistemas que combinan SQL con modelos NoSQL.  
- **Cloud Computing**: gestión de bases de datos en la nube (DBaaS).

Además, se refuerzan los mecanismos de control y seguridad, en cumplimiento de normativas como el RGPD.

## 9. VINCULACIÓN CON EL CURRÍCULO

Este tema está directamente relacionado con el módulo de Bases de Datos en el primer curso de DAM y DAW, donde los estudiantes diseñan estructuras de datos y gestionan información mediante SGBD relacionales.  
También guarda relación con el módulo de Acceso a Datos en segundo curso, donde se profundiza en el uso de SQL desde las aplicaciones.

Como ejemplo de referencia normativa en Andalucía, el Real Decreto 405/2023, de 29 de mayo, que regula las enseñanzas mínimas de los ciclos de DAM y DAW, establece la competencia de “desarrollar y gestionar sistemas de almacenamiento de información, asegurando su integridad, disponibilidad y seguridad”, lo que recoge de forma explícita los contenidos tratados en este tema.

Ejemplo práctico: diseñar la base de datos de una aplicación de gestión de tareas, creando las tablas y relaciones con SQL, y accediendo a los datos desde una aplicación en Java o Kotlin.

## 10. CONCLUSIÓN

A lo largo de este tema se han estudiado los lenguajes de definición y manipulación de datos en sistemas de bases de datos relacionales, su tipología, características y uso mediante SQL.

Dominar estos lenguajes es fundamental para garantizar la integridad, rendimiento y seguridad de los datos. Por ejemplo, en entornos profesionales como el desarrollo de aplicaciones empresariales, la correcta gestión de las estructuras y consultas SQL asegura una experiencia de usuario fiable y eficiente.

**Reflexión final**: el conocimiento de los lenguajes DDL y DML, y del lenguaje SQL en su conjunto, constituye una base imprescindible para diseñar sistemas robustos, eficientes y adaptados a las necesidades actuales de la transformación digital.

## 11. BIBLIOGRAFÍA

Joyanes, L. *Fundamentos de Programación*. McGraw-Hill.  
Prieto, A. *Introducción a la Informática*. McGraw-Hill.  
Korth, H. y Silberschatz, A. *Fundamentos de bases de datos*. McGraw-Hill.  
Tanenbaum, A. *Sistemas Operativos Modernos*. Pearson.  
Documentación oficial de Oracle Database. Disponible en: https://docs.oracle.com/en/database/  
Portal educativo Geeks for Geeks. Disponible en: https://geeksforgeeks.org
