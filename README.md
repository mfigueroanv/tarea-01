# Gestión Geoespacial de Bitácoras en Proyectos Constructivos Residenciales

## 1. Descripción General del Tema
El presente proyecto se centra en la **modernización y optimización** de los registros operativos en la industria de la construcción residencial, específicamente mediante la implementación de un Sistema de Información Geográfica (SIG) para la gestión de las bitácoras de obra. En el contexto costarricense, la bitácora es el instrumento legal y técnico donde se registran todas las incidencias, cambios, autorizaciones y avances de un proyecto. Sin embargo, su uso tradicional suele ser analógico o digital aislado, perdiendo el componente de *ubicación exacta* y la capacidad de análisis espacial masivo.

Esta propuesta de investigación surge de la necesidad de las Pequeñas y Medianas Empresas (PyMEs) constructoras de controlar proyectos que, a menudo, se encuentran geográficamente dispersos, como es común en zonas de alta plusvalía en **Guanacaste o Puntarenas**. La integración de las bitácoras en un entorno SIG permite que cada anotación técnica deje de ser un simple párrafo de texto para convertirse en un dato geoespacial con atributos temporales y técnicos vinculados a la cartografía base del proyecto (lotes, curvas de nivel, redes de servicios y niveles de construcción).

## 2. Descripción de los Datos y sus Principales Variables
Para la operatividad de este sistema, se han identificado variables críticas que deben ser capturadas y almacenadas en una base de datos espacial (PostgreSQL/PostGIS). Los datos se categorizan en tres dimensiones: espacial, temporal y descriptiva.

### 2.1 Variables Espaciales
- **Geometría de Punto:** Representa la ubicación exacta donde el inspector realiza la anotación. Se utiliza el sistema de coordenadas oficial de Costa Rica, **CRTM05**.

### 2.2 Variables Temporales y Técnicas
- **Timestamp (Sello de tiempo):** Registro automático de la fecha y hora de la entrada para evitar alteraciones posteriores y garantizar el cumplimiento de la inspección semanal.
- **Frecuencia de Inspección:** Cálculo automático de días transcurridos entre registros para alertar sobre el incumplimiento de la normativa del CFIA (inspección mínima cada 7 días naturales).

### 2.3 Variables Descriptivas y Multimedia
- **Tipo de Evento:** Clasificación mediante listas desplegables (Instrucción, Anomalía, Entrega, Cambio de Diseño).
- **Responsable:** Nombre y número de carné del profesional responsable (Ingeniero o Arquitecto).
- **Evidencia Fotográfica:** Enlaces a archivos almacenados en la nube que documentan visualmente lo descrito en el texto de la bitácora.



## 3. El Desafío de las Bitácoras en la Gestión de Obra
Uno de los problemas centrales detectados en el anteproyecto es la **fragmentación de la información**. Actualmente, un inspector puede anotar un problema estructural en una bitácora física, pero esa información no se visualiza sobre el entorno digital del proyecto hasta que ocurre una reunión de coordinación presencial. Esto genera retrasos y aumentos en los costos de corrección.

Mediante el uso de herramientas de programación en SIG, como expresiones de QGIS y scripts en Python, el sistema propuesto permite realizar un *join* espacial entre las notas de bitácora y los elementos del presupuesto. De esta manera, si una bitácora reporta un retraso en el colado de una losa, el sistema puede sombrear automáticamente esa sección en el mapa del proyecto en color rojo, alertando a la gerencia de manera visual e inmediata.

## 4. Problemas a Resolver y Preguntas de Investigación
El proyecto busca dar respuesta a las siguientes interrogantes técnicas y operativas:

1. ¿Cómo puede la georreferenciación de las bitácoras reducir el tiempo de respuesta ante incidencias técnicas en proyectos residenciales ubicados a más de 100km de la oficina central?
2. ¿Es posible automatizar la generación de reportes de cumplimiento normativo a partir de los datos espaciales capturados en campo?
3. ¿De qué manera la visualización de "mapas de calor" de incidencias en bitácoras permite identificar deficiencias sistemáticas en las cuadrillas de construcción o en los materiales utilizados?


## 5. Justificación y Alcance
La relevancia de este enfoque radica en la transparencia y la trazabilidad. Al utilizar un SIG, la bitácora se convierte en una **herramienta de auditoría irrefutable**. La posibilidad de realizar consultas espaciales (por ejemplo: *"mostrar todas las anotaciones de bitácora realizadas en el segundo nivel durante el mes de enero"*) ahorra horas de revisión manual de documentos.

Además, el sistema está diseñado para funcionar en entornos móviles, facilitando que el profesional en el sitio de obra pueda realizar los registros con un dispositivo GPS integrado. Esto asegura que la ubicación registrada sea la real, mitigando el riesgo de reportes de inspección realizados fuera del sitio de trabajo. El impacto final es una construcción más eficiente, segura y alineada con los estándares internacionales de *Project Management*.

![Imagen 1. Proyecto constructivo de Constructora El Ceibo](https://scontent.cdninstagram.com/v/t51.82787-15/649519542_18058711469679662_3676270519595347740_n.jpg?stp=dst-jpg_e35_tt6&_nc_cat=111&ccb=7-5&_nc_sid=18de74&efg=eyJlZmdfdGFnIjoiQ0xJUFMuYmVzdF9pbWFnZV91cmxnZW4uQzMifQ%3D%3D&_nc_ohc=3nJ0uDJY7q4Q7kNvwGD8bJ5&_nc_oc=AdmkwdrSL0LvDK2OS8jI-Cz1dFjNfnBbGFe8bUZYwsIRDq0fwhyjhHuyJ9Eti-BG8SQ&_nc_zt=23&_nc_ht=scontent.cdninstagram.com&_nc_gid=uaNQCL3gaDqYCYD-LJGODw&_nc_ss=8&oh=00_Afy7kJ0T6CUqD1wjjimWDMj7CpJVesnSvDOyOCEjB_K0lA&oe=69BABA4C)
<p align="center">Imagen 1. Proyecto constructivo Constructora El Ceibo.</p>

![Imagen 2. Proyecto constructivo de Constructora El Ceibo](https://scontent.fsyq1-1.fna.fbcdn.net/v/t39.30808-6/480181045_1127322509090203_5717110794894470513_n.jpg?_nc_cat=104&ccb=1-7&_nc_sid=7b2446&_nc_ohc=nWMaQR_6bnIQ7kNvwFnDgf0&_nc_oc=Adny36aAxH6xL02pSN-TrEMWMu6PpCycj_K5RE5JTmXwTaIoXNjO1pdPFdgQ-DK5gjY&_nc_zt=23&_nc_ht=scontent.fsyq1-1.fna&_nc_gid=O_RbpWYDI4_I3uX_4Emt1Q&_nc_ss=8&oh=00_AfzVFIZLz1QosZC4ISqn1Igll8gxvqOf9qu0SP7p3N0MWA&oe=69BAB0AB)
<p align="center">Imagen 2. Proyecto constructivo Constructora El Ceibo.</p>

## 6. Referencias Bibliográficas
* Consejo Federal de Ingeniería y Arquitectura (CFIA). (2019). *Reglamento para la Inspección de Obras de Edificación*. San José, Costa Rica.
* Olaya, V. (2014). *Sistemas de Información Geográfica*. Autoedición.
* Project Management Institute. (2017). *A guide to the project management body of knowledge (PMBOK guide)* (6th ed.).
* [Universidad Nacional](https://www.una.ac.cr)
* [Facebook Constructora El Ceibo](https://www.facebook.com/ConstructoraElCeibo/)
