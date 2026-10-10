# Título Proyecto

## Miembros del grupo L4-3

1. ALMERO RUIZ, FRANCISCO DE ASÍS
2. GIMENA SALAS, RODRIGO
3. SORIANO RODRIGUEZ, MIGUEL

## 1. Introducción al problema

- Descripción del problema para poner en contexto el proyecto, incluyendo información sobre los clientes y usuarios, la situación actual, problemas, expectativas, etc. Se valorará la presencia de información multimedia (fotos, gráficos, documentos escaneados, etc.).

### Contexto y descripción general

En la actualidad, la gestión de las finanzas personales constituye una actividad importante para personas de diferentes edades y situaciones económicas. Todo tipo de personas necesitan controlar sus ingresos, gastos, ahorros y presupuestos para conocer su situación económica y tomar decisiones financieras adecuadas.

Sin embargo, muchas personas realizan este seguimiento mediante métodos anticuados que no siempre permiten organizar toda su información de manera conjunta. Esta situación dificulta conocer con precisión cuánto dinero tienen disponible, identificar dónde gastan más y comprobar si están cumpliendo sus objetivos de ahorro.

El proyecto propone el diseño de una base de datos relacional en MariaDB que permita centralizar y organizar la información financiera de los usuarios. La base de datos servirá como soporte para una aplicación de gestión de finanzas personales, facilitando el registro y la consulta de cuentas bancarias, transacciones, categorías de ingresos y gastos, métodos de pago y presupuestos.

### Clientes y usuarios

Los principales clientes potenciales del sistema son personas que desean mejorar el control de sus finanzas personales sin necesidad de utilizar herramientas complejas. Entre ellos destacamos los estudiantes universitarios, los trabajadores y las familias que necesitan administrar sus ingresos y gastos habituales.

Los usuarios principales serán las propias personas que utilicen la aplicación para registrar sus movimientos financieros, consultar sus cuentas y analizar sus hábitos de consumo. También podrán establecer presupuestos mensuales por categorías, como alimentación, transporte, vivienda u ocio, con el objetivo de controlar sus gastos.

Además, contemplamos la existencia de un administrador encargado del mantenimiento técnico del sistema y de la gestión de la base de datos. Este perfil no necesita acceder al detalle de las finanzas personales de los usuarios para realizar las tareas técnicas habituales.

### Situación actual

En el presente escenario que pretendemos mejorar, la información económica de una persona puede encontrarse repartida entre distintas cuentas bancarias, aplicaciones móviles, extractos bancarios y hojas de cálculo. Aunque estas herramientas permiten consultar determinados datos, reunir toda la información y obtener una visión global de las finanzas puede requerir tiempo y trabajo manual.

Además, el registro manual de las operaciones puede provocar errores, duplicidades u omisiones. La ausencia de una clasificación homogénea de los movimientos también dificulta comparar los gastos de distintos meses o identificar cambios en los hábitos de consumo.

<figure>
  <img src="img/situacion-actual-gestion-financiera.png" alt="Situación actual de la gestión financiera" width="500">
  <figcaption>Figura 1. Situación actual de la gestión financiera.</figcaption>
</figure>

### Problemas detectados

Los principales problemas que pretendemos abordar son:

- Información dispersa: los movimientos y saldos se consultan en diferentes fuentes, lo que dificulta obtener una visión conjunta.

- Errores de registro: la introducción manual de datos puede provocar importes incorrectos, transacciones duplicadas u operaciones olvidadas.

- Falta de clasificación: si los ingresos y gastos no se organizan por categorías, resulta más difícil analizar cómo se utiliza el dinero.

- Control presupuestario limitado: sin un seguimiento periódico, el usuario puede superar el gasto que había previsto para determinadas categorías.

- Dificultad para analizar la evolución económica: comparar ingresos, gastos y ahorros entre distintos periodos puede resultar laborioso.

- Dificultad para obtener información útil: la ausencia de consultas estructuradas impide responder fácilmente a preguntas como cuál es la categoría con mayor gasto o cuánto se ha ahorrado durante un mes.

### Expectativas

Queremos hacer que los usuarios dispongan de una herramienta sencilla, organizada y fiable que les permita consultar su información financiera de forma rápida. Para satisfacer estas necesidades, el sistema deberá permitir registrar ingresos y gastos, asociarlos a cuentas y categorías, consultar saldos y analizar movimientos por fechas.

<figure>
  <img src="img/ejemplo-distribucion-gastos.png" alt="Ejemplo de distribución de gastos" width="500">
  <figcaption>Figura 2. Ejemplo de distribución de gastos mensual.</figcaption>
</figure>

Asimismo, esperamos que la aplicación facilite la creación de presupuestos mensuales y la comparación entre los importes previstos y los gastos reales. La información almacenada deberá mantener su integridad y estar protegida frente a accesos no autorizados, especialmente porque se trata de datos económicos personales.

Desde el punto de vista técnico, la base de datos deberá disponer de una estructura relacional coherente, con entidades bien definidas, relaciones entre ellas y restricciones que eviten inconsistencias. También deberá permitir realizar consultas SQL que generen información útil para los usuarios.

<figure>
  <img src="img/ejemplo-solucion-propuesta.png" alt="Ejemplo de solución propuesta" width="500">
  <figcaption>Figura 3. Ejemplo de solución propuesta.</figcaption>
</figure>

## 2. Glosario de términos

- Términos específicos del dominio del problema, ordenados alfabéticamente. Se valorará la presencia de información multimedia.

## 3. Visión general del sistema

### 3.1. Requisitos generales

### 3.2. Usuarios del sistema

## 4. Catálogo de requisitos

### 4.1. Requisitos funcionales

#### R.F.01. Título requisito funcional

Como [tipo de usuario]
quiero [servicio]
para [razón]

**Prueba de aceptación**
- Descripción de la primera comprobación a realizar
- Descripción de la segunda comprobación a realizar
- Se debe aplicar la regla de negocio R.N.XX.
- ...

#### 4.1.1. Requisitos de información

##### R.I.01. Título requisito de información

Como [tipo de usuario]
quiero [servicio]
para [razón]

**Prueba de aceptación**
- Descripción de la primera comprobación a realizar
- Descripción de la segunda comprobación a realizar
- ...

#### 4.1.2. Reglas de negocio

##### R.N.01. Título regla negocio

Descripción de la regla de negocio.

### 4.2. Mapa de historias de usuario (opcional)

### 4.3. Requisitos no funcionales (opcional)

**R.N.F. 01. Título requisito no funcional**
Como [tipo de usuario]
quiero [servicio]
para [razón]

-- fin entregable 1 --

## 5. Modelo conceptual

### 5.1. Diagramas de clases UML

- con restricciones.

### 5.2. Escenarios de prueba

- con descripción textual y diagrama de objetos UML.

## 6. Matrices de trazabilidad

- Matriz de trazabilidad entre los elementos del modelo conceptual y los requisitos.

|       | EntidadX   | AsociaciónX  | RestricciónX  | Entidad2 ...   | 
|:------|:-----------|:-----------|:-----------|:-----------|
| RI-1  | X          | X          | X          | X          |
| RI-2  |            | X          |            | X          |
| RF-1  |            | X          |            | X          |
| RF-2  | X          |            | X          | X          |
| RN-1  |            | X          |            |            |
| RN-2  | X          | X          | X          |            |
| ...   |            |            |            |            |

-- fin entregable 2 --

## 7. Modelo relacional en 3FN

- Relaciones obtenidas al aplicar la transformación del modelo conceptual.

### 7.1.  Justificación de la estrategia de transformación de jerarquías

- si se identificaron jerarquías en el MC.


### 8. Matriz de trazabilidad MC/SQL (opcional):

- Restricciones sobre el MC / Elementos del modelo tecnológico (SQL) (Triggers, checks, etc.)
- Incluir Reglas de negocio — Constraints/Triggers en las matrices de trazabilidad para el entregable 3

|       | EntidadX   | AsociaciónX  | RestricciónX  | Entidad2 ...   | 
|:-------|:-------|:-------|:-------|:-------|
| TABLA-1 |        |        |        |        |
| TABLA-2 |        |        |        |        |
| TABLA-3 |        |        |        |        |
| TABLA-4 |        |        |        |        |
| TRIG-1 |        |        |        |        |
| TRIG-2 | X      | X      |        | X      |
| TRIG-3 |        | X      |        | X      |
| TRIG-4 |        |        | X      |        |
| CONST-1 |        |        |        |        |
| CONST-2 | X      | X      |        | X      |
| CONST-3 |        | X      |        | X      |
| CONST-4 |        |        | X      |        |

Se consideran todo tipo de constraints declarativas (aquellas definidas durante el CREATE TABLE).
-- fin entregable 3 --

## Referencias


