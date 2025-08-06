
# Sistema de Gestión de Gages

Sistema de Gestión de Gages para Control de Calibración. Este proyecto tiene como objetivo desarrollar una aplicación para la gestión de instrumentos de medición (gages) en la empresa AUMA Chihuahua S.A. de C.V., específicamente para el área de metrología. Surge ante la necesidad de sustituir el sistema anterior que dejó de ser compatible con versiones actuales de Windows.

## Tabla de contenidos
1. [Descripción](#descripción)
2. [Problema identificado](#problema-identificado)
3. [Solución propuesta](#solución-propuesta)
4. [Arquitectura](#arquitectura)
5. [Propósito](#propósito)
6. [Funcionalidades principales](#funcionalidades-principales)
7. [Requerimientos](#requerimientos)
8. [Instalación](#instalación)
9. [Configuración](#configuración)
10. [Uso](#uso)
11. [Contribución](#contribución)
12. [Roadmap](#roadmap)
13. [Seguridad](#seguridad)
14. [Estado del proyecto](#estado-del-proyecto)
15. [Autor](#autor)
16. [Licencia](#licencia)

## Descripción
Aplicación desarrollada en Java con interfaz gráfica para el registro, trazabilidad y control de calibración de instrumentos de medición (gages), compatible con sistemas operativos Windows modernos.

## Problema identificado
El sistema anterior ya no es funcional con las actualizaciones recientes de Windows, dificultando el registro, trazabilidad y consulta de los instrumentos de medición. Además, el proceso era manual, lo cual incrementaba errores y retrasos.

## Solución propuesta
Se desarrolló una aplicación que permite:
- Registro y consulta de información de calibración.
- Alta masiva de gages vía archivos Excel y MySQL.
- Filtro por fechas de vencimiento.
- Control de usuarios y trazabilidad.
- Generación de reportes.
- Integración con GitHub para gestión de código.

## Arquitectura
Esta se basa en el patrón cliente-servidor. El sistema está construido en Java utilizando NetBeans, con pruebas automatizadas en JUnit. El repositorio de código está alojado en GitHub, y se integran Actions de GitHub para validación automática. El diseño considera despliegue local con posibilidad futura de migración a la nube.

<img width="730" height="492" alt="image" src="https://github.com/user-attachments/assets/51509a06-2af2-4587-8fc6-de29274f2345" />


## Propósito
Brindar una solución moderna, sencilla y funcional que permita:
- Registrar y consultar información de calibración.
- Filtrar gages próximos a vencer.
- Garantizar trazabilidad y control metrológico.
- Evitar el uso de gages vencidos mediante alertas visuales.
- Reforzar la seguridad mediante autenticación de usuario.

## Funcionalidades principales
- Inicio de sesión con usuario y contraseña.
- Alta masiva de gages mediante archivo Excel estructurado.
- Registro manual de datos clave: código, cliente, área, responsable, fecha de calibración.
- Cálculo automático de fecha de vencimiento.
- Consulta y filtrado de gages por vencimiento.
- Respaldo y almacenamiento local en archivo Excel.
- Interfaz sencilla y ligera compatible con Windows 10 o superior.

## Requerimientos

### a. Servidores de aplicación, web, bases de datos, etc.
- **Servidor de Aplicaciones:** GlassFish Server (Java EE 8)
- **Servidor Web:** Integrado con GlassFish
- **Base de Datos:** MySQL o PostgreSQL (local o en red LAN)
- **Repositorio de código:** GitHub

### b. Paquetes adicionales
- **JDK:** Oracle JDK u OpenJDK 8+
- **JUnit:** Para pruebas automatizadas
- **Bibliotecas de Apache POI:** Para lectura/escritura de archivos Excel (.xlsx)
- **JDBC:** Conector de base de datos correspondiente (MySQL Connector/J o PostgreSQL JDBC)

### c. Versión de Java, etc.
- **Java:** Versión 8 o superior
- **NetBeans:** Versión 12.2 o superior
- **SO compatible:** Windows 10 o superior
- **Office:** Microsoft Excel para manejo de archivos `.xlsx`

## Instalación
### a. ¿Cómo instalar el ambiente de desarrollo?
1. Descargar e instalar JDK 8+.
2. Descargar NetBeans 12.2 o superior.
3. Clonar el repositorio con `git clone https://github.com/manuelsanchez1986/sistema-gestion-gages.git`
4. Abrir el proyecto en NetBeans y configurar el servidor GlassFish.
5. Crear la base de datos (MySQL o PostgreSQL) y configurar la conexión JDBC.

### b. ¿Cómo ejecutar pruebas manualmente?
- Usar JUnit desde NetBeans: clic derecho sobre los archivos de prueba y seleccionar “Test File”.

### c. ¿Cómo implementar la solución en producción?
- Para ambiente local: usar GlassFish y base de datos local.
- Para despliegue en la nube: adaptar configuración a servicios como Heroku con base de datos remota.

## Configuración
### a. Configuración del producto (archivos de configuración)
- Archivo `.properties` o `.xml` con rutas de base de datos, parámetros de sesión y rutas de respaldo.

### b. Configuración de los requerimientos
- Dependencias: agregar bibliotecas Apache POI, JDBC, JUnit.
- Configuración del entorno: puerto GlassFish, credenciales de conexión, permisos.

## Uso
### a. Sección de referencia para usuario final
- Manual PDF y en línea describiendo paso a paso el uso del sistema, filtros y reportes.
Este sistema permite a los usuarios registrar, consultar y filtrar información sobre instrumentos de medición (gages) de manera fácil.
A continuación, se describe el uso básico paso a paso:

1. Inicio de sesión
Abre la aplicación desde el acceso directo o ejecutable .jar.
Ingresa tu usuario y contraseña proporcionados por el administrador.
Haz clic en "Iniciar sesión".

2. Carga de gages desde Excel
Ve al menú Archivo > Importar gages.
Selecciona el archivo .xlsx con el formato establecido (código, cliente, área, etc.).
Verifica los datos cargados y confirma el registro.

3. Consulta de gages
Usa la barra de búsqueda para localizar un gage por código o cliente.
Aplica filtros por:
Fecha de calibración
Fecha de vencimiento
Responsable

4. Exportar reporte
Ve a Archivo > Exportar.
Elige formato de exportación (Excel o PDF).
Se generará un archivo con todos los gages visibles en pantalla.

### b. Sección de referencia para usuario administrador
- Manual de administración de usuarios, configuración de base de datos y respaldo.
Gestión de usuarios
Menú Administración > Usuarios.
Puedes:
Crear nuevos usuarios
Asignar roles (usuario / administrador)
Editar contraseñas
Eliminar accesos

2. Configuración de base de datos
El archivo de configuración (config.properties) permite cambiar parámetros como:
IP del servidor de base de datos
Puerto
Usuario y contraseña de la DB
Asegúrate de reiniciar la aplicación tras realizar cambios.

3. Respaldo de datos
Ve a Administración > Exportar respaldo.
Esto generará un archivo Excel con toda la base de datos actual.
Se recomienda hacer respaldo semanal o antes de realizar cambios masivos.

4. Supervisión de registros
Desde el módulo de Historial puedes ver:
Qué usuario modificó qué gage.
Fecha y hora de cada operación.
Cualquier error de carga o ingreso fallido.

## Contribución
### a. Guía de contribución para usuarios
1. Clonar repositorio con `git clone`
2. Crear nuevo branch `git checkout -b feature/nombre`
3. Hacer cambios y commitear `git commit -m "mensaje"`
4. Subir branch `git push origin feature/nombre`
5. Hacer pull request

### b. Consideraciones
- Revisión de código con pruebas.
- Validación antes del merge.

## Roadmap
Estas son algunas funcionalidades que se planean agregar en futuras versiones del sistema:

- Alertas automáticas por correo electrónico para gages próximos a vencer.
- Historial de calibraciones por gage (con auditoría completa).
- Implementación de dashboard con gráficas de control.
- Soporte multiplataforma (versión web).
- Backup automático de la base de datos al iniciar/cerrar sesión.
- Soporte para escáner de código QR en el registro y búsqueda de gages.

## Seguridad
El sistema requiere autenticación con usuario y contraseña para garantizar que solo personal autorizado tenga acceso al registro y consulta de información metrológica.

## Estado del proyecto
**En desarrollo**  
Sprint 1: Implementación de inicio de sesión, carga masiva y registro manual.

## Autor
**Manuel Aarón Sánchez Gutiérrez**  
Metrologista – AUMA Chihuahua  
Correo: al03053351@tecmilenio.mx / manuel.sanchez@bocar.com

## Licencia
Este proyecto se utiliza con fines educativos. Para uso comercial o industrial, contactar con el autor.
