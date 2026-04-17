# SISTEMA-DE-GESTION-ACADEMICA-SQL

## Descripción

Este proyecto contiene el script SQL para el Caso de Estudio 2 del curso SC404. El sistema está diseñado para gestionar información académica de una institución educativa, incluyendo alumnos, docentes, cursos, especialidades y oficinas.

## Base de Datos

**Nombre de la base de datos:** `SC404_CASOESTUDIO2_G7`

## Estructura de Tablas

El sistema está compuesto por las siguientes tablas:

### 1. FIDE_ESTADOS_TB
Tabla maestra que almacena los diferentes estados del sistema.
- `ID_ESTADO` (INT, PK, IDENTITY): Identificador único del estado
- `NOMBRE_ESTADO` (NVARCHAR(50)): Nombre del estado

### 2. FIDE_CURSO_TB
Almacena información de los cursos disponibles.
- `ID_CURSO` (INT, PK, IDENTITY): Identificador único del curso
- `NOMBRE_CURSO` (NVARCHAR(100)): Nombre del curso
- `ID_ESTADO` (INT, FK): Referencia al estado del curso

### 3. FIDE_ESPECIALIDAD_TB
Gestiona las especialidades académicas.
- `ID_ESPECIALIDAD` (INT, PK, IDENTITY): Identificador único de la especialidad
- `NOMBRE_ESPECIALIDAD` (NVARCHAR(100)): Nombre de la especialidad
- `ID_ESTADO` (INT, FK): Referencia al estado de la especialidad

### 4. FIDE_ALUMNO_TB
Almacena información de los alumnos.
- `ID_ALUMNO` (INT, PK, IDENTITY): Identificador único del alumno
- `NOMBRE_ALUMNO` (NVARCHAR(100)): Nombre del alumno
- `APELLIDO_PATERNO` (NVARCHAR(100)): Apellido paterno
- `APELLIDO_MATERNO` (NVARCHAR(100)): Apellido materno
- `ID_ESPECIALIDAD` (INT, FK): Referencia a la especialidad del alumno
- `ID_CURSO` (INT, FK): Referencia al curso del alumno
- `ID_ESTADO` (INT, FK): Referencia al estado del alumno

### 5. FIDE_OFICINA_TB
Gestiona las oficinas disponibles.
- `ID_OFICINA` (INT, PK, IDENTITY): Identificador único de la oficina
- `NOMBRE_OFICINA` (NVARCHAR(100)): Nombre de la oficina
- `ID_ESTADO` (INT, FK): Referencia al estado de la oficina

### 6. FIDE_DOCENTE_TB
Almacena información de los docentes.
- `ID_DOCENTE` (INT, PK, IDENTITY): Identificador único del docente
- `NOMBRE_DOCENTE` (NVARCHAR(100)): Nombre del docente
- `APELLIDO_PATERNO` (NVARCHAR(100)): Apellido paterno
- `APELLIDO_MATERNO` (NVARCHAR(100)): Apellido materno
- `ID_OFICINA` (INT, FK): Referencia a la oficina del docente
- `ID_CURSO` (INT, FK): Referencia al curso que imparte el docente
- `ID_ESTADO` (INT, FK): Referencia al estado del docente

## Procedimientos Almacenados

El script incluye los siguientes procedimientos almacenados para la inserción de datos:

- `SP_INSERTAR_ESTADO`: Inserta un nuevo estado
- `SP_INSERTAR_CURSO`: Inserta un nuevo curso
- `SP_INSERTAR_ESPECIALIDAD`: Inserta una nueva especialidad
- `SP_INSERTAR_OFICINA`: Inserta una nueva oficina
- `SP_INSERTAR_ALUMNO`: Inserta un nuevo alumno
- `SP_INSERTAR_DOCENTE`: Inserta un nuevo docente

Todos los procedimientos incluyen manejo de errores mediante bloques TRY-CATCH.

## Datos de Ejemplo

El script incluye datos de ejemplo para todas las tablas:

### Estados
- Activo
- Inactivo
- Suspendido
- En Proceso
- Finalizado

### Especialidades
- Industrial
- Sistemas
- Civil
- Mecánica
- Electrónica

### Cursos
- Matemática 2
- Física Química
- Descriptiva
- Investigación 1
- Programación 1

### Oficinas
- CB-214
- CB-110
- CB-120
- SC-220
- CB-101

## Requisitos

- SQL Server (versión compatible con IDENTITY y procedimientos almacenados)
- Permisos para crear bases de datos y procedimientos almacenados

## Instalación

1. Abre SQL Server Management Studio (SSMS) o tu cliente SQL preferido
2. Conéctate a tu instancia de SQL Server
3. Abre el archivo `G7_SC404_MN_CasoEstudio2.sql`
4. Ejecuta el script completo

El script realizará las siguientes acciones:
- Creará la base de datos `SC404_CASOESTUDIO2_G7`
- Creará todas las tablas con sus relaciones
- Creará los procedimientos almacenados
- Insertará los datos de ejemplo
- Mostrará la verificación de los datos insertados

## Notas

- El script incluye algunas duplicaciones en la creación de tablas (líneas 7-67 y 79-140), pero esto no afecta la ejecución ya que SQL Server manejará los errores si las tablas ya existen.
- Todos los datos de ejemplo se insertan con estado "Activo" (ID_ESTADO = 1).
- El script utiliza la codificación NVARCHAR para soportar caracteres especiales y acentos.

## Autor

Grupo 7 - SC404

## Licencia

Este proyecto es parte de un caso de estudio académico.

