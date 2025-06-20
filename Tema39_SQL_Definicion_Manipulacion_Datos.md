
# TEMA 39: Lenguajes para la definición y manipulación de datos en sistemas de bases de datos relacionales. Tipos. Características. Lenguaje SQL.

## ÍNDICE
1. INTRODUCCIÓN  
2. TIPOS DE LENGUAJES EN SISTEMAS DE BASES DE DATOS RELACIONALES  
3. LENGUAJE DE DEFINICIÓN DE DATOS (DDL)  
4. LENGUAJE DE MANIPULACIÓN DE DATOS (DML)  
5. CARACTERÍSTICAS DE LOS LENGUAJES DDL Y DML  
6. LENGUAJE SQL  
6.1. DDL en SQL  
6.2. DML en SQL  
7. DICCIONARIO DE DATOS  
8. TENDENCIAS ACTUALES  
9. VINCULACIÓN CON EL CURRÍCULO  
10. CONCLUSIÓN  
11. BIBLIOGRAFÍA  

## 1. INTRODUCCIÓN

En la era digital, las bases de datos relacionales resultan esenciales para gestionar grandes volúmenes de información en aplicaciones cotidianas como registros web, compras online o reservas.

Antes de la aparición de los sistemas gestores de bases de datos (SGBD), los sistemas de archivos requerían modificar todos los programas ante cualquier cambio estructural en los datos. Para superar esta limitación surgieron los SGBD, que separan los datos de las aplicaciones y han transformado el modo de almacenar, consultar y compartir datos.

Según Korth y Silberschatz, en *Fundamentos de bases de datos*, comprender su funcionamiento es esencial para diseñar soluciones eficaces de almacenamiento, análisis y procesamiento de datos. Este conocimiento resulta imprescindible tanto en el entorno académico como en el profesional.

Este tema se centra en los lenguajes para la **definición** y **manipulación** de datos en bases de datos relacionales, analizando sus tipos, características y, en especial, el papel del lenguaje SQL como estándar predominante.

En la actualidad, estos lenguajes son fundamentales en entornos como la inteligencia artificial (IA), el big data y la computación en la nube, donde la gestión avanzada y flexible de datos es crítica.

## 2. TIPOS DE LENGUAJES EN SISTEMAS DE BASES DE DATOS RELACIONALES

En un SGBD relacional se emplean diferentes tipos de lenguajes según la operación a realizar:

- **Lenguaje de Definición de Datos (DDL)**: define las estructuras (tablas, índices, vistas).
- **Lenguaje de Manipulación de Datos (DML)**: gestiona la consulta y modificación de los datos.
- **Lenguaje de Control de Datos (DCL)**: gestiona permisos y accesos.
- **Lenguaje de Control de Transacciones (TCL)**: asegura la consistencia de las transacciones.

Aunque en este tema nos centraremos en los lenguajes **DDL y DML**, es importante conocer que un SGBD completo integra también DCL y TCL para una gestión avanzada y segura.

## 3. LENGUAJE DE DEFINICIÓN DE DATOS (DDL)

El DDL es el sublenguaje que permite definir y modificar la estructura de una base de datos. Entre sus comandos básicos se encuentran:

- `CREATE`: creación de bases de datos, tablas, vistas, índices.
- `ALTER`: modificación de estructuras.
- `DROP`: eliminación de objetos de la base de datos.
- `TRUNCATE`: eliminación rápida del contenido de una tabla.

El uso del DDL resulta fundamental en las fases iniciales del diseño de bases de datos, permitiendo establecer de forma explícita los elementos que las componen y sus restricciones.

## 4. LENGUAJE DE MANIPULACIÓN DE DATOS (DML)

El DML permite realizar operaciones sobre los datos: consultar, insertar, modificar y eliminar registros. Los comandos básicos son:

- `SELECT`: consulta de datos.
- `INSERT`: inserción de nuevos registros.
- `UPDATE`: actualización de registros existentes.
- `DELETE`: eliminación de registros.

Su uso es habitual tanto en operaciones cotidianas como en procesos automáticos, permitiendo a los usuarios acceder y gestionar eficazmente la información.

## 5. CARACTERÍSTICAS DE LOS LENGUAJES DDL Y DML

Según Prieto en *Introducción a la Informática*, la definición clara y estructurada de los lenguajes en un SGBD favorece la portabilidad, flexibilidad y rendimiento del sistema.

Entre sus principales características destacan:

- **Declarativos**: describen qué se desea lograr, sin especificar cómo.
- **Simplicidad**: comandos accesibles incluso a usuarios no expertos.
- **Independencia**: permiten desacoplar los datos de la lógica de aplicación.
- **Estandarización**: SQL es un lenguaje normalizado (ISO/IEC 9075), soportado por la mayoría de SGBD.

## 6. LENGUAJE SQL

El SQL (*Structured Query Language*) es el estándar de facto en los SGBD relacionales. Es un lenguaje declarativo que integra DDL, DML, DCL y TCL, proporcionando un marco completo para la gestión de datos.

### 6.1. DDL en SQL

```sql
CREATE DATABASE GestionAlumnos;

CREATE TABLE Alumnos (
    id INT PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    fecha_nacimiento DATE,
    nota_final DECIMAL(5,2)
);

ALTER TABLE Alumnos
ADD email VARCHAR(100);

DROP TABLE Alumnos;

CREATE INDEX idx_nombre ON Alumnos(nombre);

CREATE VIEW VistaAprobados AS
SELECT id, nombre, nota_final
FROM Alumnos
WHERE nota_final >= 5.0;
```

### 6.2. DML en SQL

```sql
INSERT INTO Alumnos (id, nombre, fecha_nacimiento, nota_final)
VALUES (1, 'Ana Torres', '2003-05-14', 8.5);

SELECT nombre, nota_final
FROM Alumnos
WHERE nota_final >= 5.0
ORDER BY nota_final DESC;

UPDATE Alumnos
SET nota_final = 9.0
WHERE id = 1;

DELETE FROM Alumnos
WHERE id = 1;
```

## 7. DICCIONARIO DE DATOS

El **diccionario de datos** es un componente interno del SGBD que almacena metadatos: descripciones de tablas, columnas, índices, restricciones, usuarios y permisos.

Según Joyanes en *Fundamentos de Programación*, la correcta organización de los metadatos mejora la eficiencia y seguridad del sistema, facilitando el mantenimiento y la evolución de la base de datos.

```sql
SELECT table_name, column_name, data_type
FROM information_schema.columns
WHERE table_name = 'Alumnos';
```

## 8. TENDENCIAS ACTUALES

- Incorporación de **extensiones NoSQL** en motores relacionales.
- Optimización automática de consultas mediante **IA**.
- **Automatización de DDL**.
- **SQL On-Demand** en servicios cloud.

Según Tanenbaum en *Sistemas Operativos Modernos*, la escalabilidad y seguridad de los nuevos modelos de bases de datos dependen en gran medida de un uso correcto de los lenguajes DDL y DML.

## 9. VINCULACIÓN CON EL CURRÍCULO

Este tema está directamente relacionado con el módulo de **Bases de Datos** en DAM y DAW, así como en **Acceso a Datos**.

Como referencia normativa en Andalucía, el Real Decreto 405/2023 establece la competencia de “desarrollar y gestionar sistemas de almacenamiento de información, asegurando su integridad, disponibilidad y seguridad”.

## 10. CONCLUSIÓN

Dominar el DDL permite diseñar estructuras robustas y flexibles, mientras que el uso adecuado del DML asegura una gestión eficiente y segura de los datos. El conocimiento de SQL es una competencia esencial para el profesional de la informática.

## 11. BIBLIOGRAFÍA

- Joyanes, L. *Fundamentos de Programación*. McGraw-Hill.  
- Prieto, A. *Introducción a la Informática*. McGraw-Hill.  
- Korth, H. y Silberschatz, A. *Fundamentos de bases de datos*. McGraw-Hill.  
- Tanenbaum, A. *Sistemas Operativos Modernos*. Pearson.  
- Documentación oficial de Oracle Database: <https://docs.oracle.com/en/database/>  
- Portal educativo Geeks for Geeks: <https://geeksforgeeks.org>  
