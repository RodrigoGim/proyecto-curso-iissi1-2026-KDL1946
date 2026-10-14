# Gestor De Finanzas Personales

## Miembros del grupo L4-3

1. ALMERO RUIZ, FRANCISCO DE ASÍS
2. GIMENA SALAS, RODRIGO
3. SORIANO RODRIGUEZ, MIGUEL

## 1. Introducción al problema

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

- Administrador: persona encargada del mantenimiento técnico del sistema. Gestiona las categorías generales y los usuarios, pero no consulta los datos económicos de nadie.
  
- Ahorro: diferencia entre los ingresos y los gastos de un usuario en un periodo (normalmente un mes). Si sale negativo, ese mes se ha gastado más de lo que se ha ingresado.
  
- Categoría: etiqueta que sirve para clasificar un movimiento según su naturaleza (Alimentación, Transporte, Ocio, Nómina...). Cada categoría es de ingreso o de gasto. Las categorías generales las crea el administrador y las personales las crea cada usuario para su uso propio.

- Cliente: persona registrada que usa la aplicación para gestionar su propio dinero. A lo largo del documento usamos "cliente" y "usuario" como sinónimos, salvo cuando hablamos del administrador.

- Cuenta: lugar donde el usuario tiene su dinero y del que quiere llevar el control. Puede ser una cuenta bancaria (corriente o de ahorro), una tarjeta o el dinero en efectivo. Cada cuenta tiene un saldo y una moneda.

- Domiciliación: forma de pago en la que una empresa cobra directamente de la cuenta del usuario de forma periódica, por ejemplo el recibo de la luz o del gimnasio.

- Gasto: movimiento que hace que disminuya el saldo de una cuenta, por ejemplo una compra en el supermercado.

- Gasto real: suma de todos los gastos que un usuario ha hecho en una categoría durante un mes. Es lo que se compara con el presupuesto.

- Ingreso: movimiento que hace que aumente el saldo de una cuenta, por ejemplo cobrar la nómina o una beca.

- Método de pago: forma en la que se ha realizado un movimiento: efectivo, tarjeta, Bizum, domiciliación o transferencia bancaria.

- Moneda: divisa en la que está expresado el saldo de una cuenta (EUR, USD...). Por defecto se usa el euro.

- Movimiento: cualquier ingreso o gasto registrado en una cuenta. Siempre tiene un importe, una fecha, un tipo y una categoría.

- Presupuesto: cantidad máxima que un usuario se propone gastar en una categoría de gasto durante un mes concreto.

- Saldo: dinero disponible en una cuenta en un momento dado. Se calcula a partir del saldo inicial sumando los ingresos y restando los gastos.

- Transferencia: paso de dinero de una cuenta (origen) a otra (destino). Es interna si las dos cuentas son del mismo usuario (por ejemplo, pasar dinero de la cuenta corriente a la de ahorro) y externa si la cuenta destino es de otro usuario.

## 3. Visión general del sistema

### 3.1. Requisitos generales

#### R.G.01. Gestionar las cuentas
  Como cliente, quiero tener todas mis cuentas (bancarias, tarjetas y efectivo) en una misma aplicación, para saber en todo momento cuánto dinero tengo y dónde.

#### R.G.02. Controlar los ingresos y gastos
  Como cliente, quiero registrar mis ingresos y gastos clasificados por categorías, para saber en qué me gasto el dinero.

#### R.G.03. Mover dinero entre cuentas
  Como cliente, quiero registrar las transferencias entre mis cuentas y con otros usuarios, para que los saldos de todas mis cuentas estén siempre actualizados.

#### RG.04. Planificar con presupuestos
  Como cliente, quiero fijar un límite de gasto mensual por categoría, para no gastar más de lo que tenía previsto.

#### R.G.05. Analizar la situación económica
  Como cliente, quiero consultar resúmenes de mis ingresos, gastos y ahorro por meses, para ver cómo evolucionan mis finanzas y tomar mejores decisiones.

#### R.G.06. Mantener el sistema
  Como administrador, quiero gestionar los usuarios y las categorías generales, para que la aplicación funcione correctamente y sea igual para todos.

### 3.2. Usuarios del sistema

- Cliente (usuario registrado): es el usuario principal del sistema. Se registra con su email, da de alta sus cuentas, registra sus movimientos y transferencias, crea sus presupuestos y categorías personales y consulta toda su información. Solo puede ver y modificar sus propios datos. No hace falta que tenga conocimientos de informática ni de contabilidad, por lo que el sistema tiene que ser fácil de usar.

- Administrador: se encarga del mantenimiento de la aplicación y de la base de datos. Crea y modifica las categorías generales que tienen disponibles todos los clientes (por ejemplo "Alimentación", "Vivienda" o "Nómina") y puede consultar y dar de baja usuarios. Por motivos de privacidad, no tiene acceso a los saldos, movimientos ni presupuestos de los clientes.

Hemos decidido no incluir usuarios anónimos, ya que toda la información del sistema es personal y no tiene sentido consultarla sin estar registrado.

## 4. Catálogo de requisitos

### 4.1. Requisitos funcionales

#### R.F.01. Listado de cuentas y saldo total

Como cliente, quiero ver un listado de mis cuentas activas con el saldo de cada una y el saldo total, para saber cuánto dinero tengo en total sin tener que mirar cada banco por separado.

**Prueba de aceptación**
- Un usuario con dos cuentas de 300 € y 700 € pide el listado y le aparecen las dos cuentas y un total de 1000 €.
- Las cuentas inactivas no aparecen en el listado ni cuentan en el total.
- Un usuario sin cuentas pide el listado y aparece vacío con un total de 0 €.

#### R.F.02. Consulta de movimientos por fechas

Como cliente, quiero consultar los movimientos de una cuenta entre dos fechas, ordenados del más reciente al más antiguo, pudiendo filtrar por tipo o por categoría, para revisar en qué he gastado el dinero en un periodo concreto.

**Prueba de aceptación**
- Se piden los movimientos del 1 al 31 de marzo y solo aparecen los de esas fechas, empezando por el más reciente.
- Se piden los movimientos de marzo filtrando por la categoría "Ocio" y solo aparecen los de esa categoría.
- Un usuario intenta consultar los movimientos de una cuenta que no es suya y se rechaza.

#### R.F.03. Resumen mensual

Como cliente, quiero ver para un mes concreto el total de ingresos, el total de gastos y el ahorro, para saber si ese mes he ahorrado o he gastado más de lo que he ingresado.

**Prueba de aceptación**
- En marzo hay ingresos por 1200 € y gastos por 900 €; el resumen muestra un ahorro de 300 €.
- Si en un mes los gastos superan a los ingresos, el ahorro aparece en negativo.
- Una transferencia interna entre dos cuentas del mismo usuario no cuenta ni como ingreso ni como gasto en el resumen.

#### R.F.04. Gasto por categorías

Como cliente, quiero ver cuánto he gastado en cada categoría en un mes y qué porcentaje supone del gasto total, ordenado de mayor a menor, para saber en qué se me va más el dinero.

**Prueba de aceptación**
- En marzo se gastan 600 € en "Vivienda" y 200 € en "Ocio"; el listado muestra primero "Vivienda" con un 75 % y después "Ocio" con un 25 %.
- Las categorías en las que no hay gastos ese mes no aparecen en el listado.
- Se debe aplicar la regla de negocio R.N.05.

#### R.F.05. Seguimiento de presupuestos

Como cliente, quiero ver, para cada presupuesto de un mes, el importe previsto, el gasto real y lo que me queda por gastar, para controlar si voy bien durante el mes.

**Prueba de aceptación**
- Con un presupuesto de 300 € para "Ocio" y 120 € gastados, aparece un gasto real de 120 € y un restante de 180 €.
- Los presupuestos inactivos no aparecen en el listado.
- Se debe aplicar la regla de negocio R.N.11.

#### R.F.06. Presupuestos superados

Como cliente, quiero ver un listado de los presupuestos en los que he gastado más de lo previsto y en cuánto me he pasado, para saber en qué categorías tengo que recortar.

**Prueba de aceptación**
- Con un presupuesto de 300 € para "Ocio" y 350 € gastados, aparece en el listado con un exceso de 50 €.
- Un presupuesto en el que no se ha superado el importe previsto no aparece en el listado.
- Se debe aplicar la regla de negocio R.N.11.
  
#### R.F.07. Historial de transferencias

Como cliente, quiero consultar las transferencias que he enviado y recibido, indicando si son internas o externas, para tener controlado el dinero que muevo.

**Prueba de aceptación**
- Un usuario envía una transferencia y recibe otra; las dos aparecen en su historial, una como enviada y otra como recibida.
- Una transferencia entre dos cuentas del mismo usuario aparece como interna.
- Se debe aplicar la regla de negocio R.N.06.
  
#### R.F.08. Evolución del gasto de una categoría

Como cliente, quiero ver lo que he gastado en una categoría en cada uno de los últimos 6 meses, para ver si mis hábitos de consumo están cambiando.

**Prueba de aceptación**
- Se pide la evolución de "Transporte" y aparecen los últimos 6 meses con su gasto.
- Los meses en los que no hay gastos en esa categoría aparecen con 0 €.
  
#### R.F.09. Listado de usuarios

Como administrador, quiero ver un listado de los usuarios registrados con su fecha de alta y su número de cuentas, para hacer el mantenimiento del sistema sin acceder a sus datos económicos.

**Prueba de aceptación**
- El administrador pide el listado y aparecen todos los usuarios con su fecha de alta y número de cuentas, pero sin saldos ni movimientos.
- Un cliente intenta pedir este listado y se rechaza por no tener permisos.
- Se debe cumplir el requisito no funcional R.N.F.01.

#### 4.1.1. Requisitos de información

##### R.I.01. Usuario:

Como administrador, quiero disponer de la siguiente información sobre los usuarios: nombre y apellidos, email, contraseña, fecha de alta y rol (cliente o administrador), para poder identificar a cada usuario y saber qué puede hacer en el sistema.

**Prueba de aceptación**
- Se registra un usuario con todos sus datos, se pide el listado de usuarios y aparece el nuevo usuario.
- Se intenta registrar un usuario sin email, nombre o contraseña y se recibe un error por faltar datos obligatorios.
- Se registra un usuario sin indicar la fecha de alta y se guarda con la fecha actual.
- Se debe aplicar la regla de negocio R.N.01.

##### R.I.02. Cuentas:

Como cliente, quiero disponer de la siguiente información sobre mis cuentas: usuario titular, nombre de la cuenta (por ejemplo "Cuenta nómina" o "Hucha"), tipo de cuenta (corriente, ahorro, tarjeta o efectivo), saldo actual, moneda, fecha de apertura y si está activa o no, para poder gestionar todas mis cuentas en una sola aplicación.

**Prueba de aceptación**
- Un usuario crea una cuenta con un saldo inicial de 1000 €, pide el listado de sus cuentas y aparece la nueva cuenta con ese saldo.
- Se crea una cuenta sin indicar la moneda y se guarda en euros (EUR).
- Se crea una cuenta sin indicar si está activa y se guarda como activa.
- Se intenta crear una cuenta para un usuario que no existe y se recibe un error.
- Se debe aplicar la regla de negocio R.N.02.
- Se debe aplicar la regla de negocio R.N.07.

##### R.I.03. Movimientos:

Como cliente, quiero disponer de la siguiente información sobre mis movimientos: cuenta en la que se realiza, tipo (ingreso o gasto), categoría, importe, fecha del movimiento, método de pago (efectivo, tarjeta, Bizum, domiciliación o transferencia, opcional), descripción (opcional) y fecha de registro en el sistema, para tener un registro de todo el dinero que entra y sale de mis cuentas.

**Prueba de aceptación**
- Se registra un gasto de 25 € en la cuenta "Cuenta nómina" con categoría "Alimentación", se piden los movimientos de esa cuenta y aparece el gasto.
- Se registra un movimiento sin descripción ni método de pago y se guarda correctamente.
- Se intenta registrar un movimiento sin cuenta, sin importe o sin fecha y se recibe un error.
- Se debe aplicar la regla de negocio R.N.03.
- Se debe aplicar la regla de negocio R.N.04.
- Se debe aplicar la regla de negocio R.N.05.

##### R.I.04. Categorias:

Como cliente, quiero disponer de la siguiente información sobre las categorías: nombre, tipo (ingreso o gasto), si es general o personal y, si es personal, el usuario que la ha creado, para poder clasificar mis movimientos.

**Prueba de aceptación**
- El administrador crea la categoría general "Vivienda" de tipo gasto, se pide el listado de categorías y aparece.
- Un cliente crea la categoría personal "Gimnasio" de tipo gasto; aparece en su listado de categorías pero no en el de otro cliente.
- Se intenta crear una categoría con un tipo distinto de ingreso o gasto y se recibe un error.
- Se debe aplicar la regla de negocio R.N.08.

##### R.I.05. Transferencias:

Como cliente, quiero disponer de la siguiente información sobre las transferencias: cuenta de origen, cuenta de destino, importe, fecha, concepto (opcional) y tipo (interna o externa, que se calcula según si las dos cuentas son del mismo usuario), para saber qué dinero he movido entre cuentas y a quién.

**Prueba de aceptación**
- Se registra una transferencia de 200 € entre dos cuentas, se pide el historial de transferencias y aparece.
- Se registra una transferencia sin concepto y se guarda correctamente.
- Se intenta registrar una transferencia a una cuenta que no existe o sin indicar la cuenta destino y se recibe un error.
- Se debe aplicar la regla de negocio R.N.03.
- Se debe aplicar la regla de negocio R.N.06.

##### R.I.06. Presupuestos:

Como cliente, quiero disponer de la siguiente información sobre mis presupuestos: usuario al que pertenece, categoría de gasto que se presupuesta, importe máximo previsto, mes y año, y si está activo o no, para planificar cuánto quiero gastar cada mes.

**Prueba de aceptación**
- Un usuario crea un presupuesto de 300 € para "Ocio" en marzo de 2026, pide sus presupuestos y aparece.
- Se intenta crear un presupuesto sin categoría, sin mes o sin importe y se recibe un error.
- Se debe aplicar la regla de negocio R.N.03.
- Se debe aplicar la regla de negocio R.N.09.
- Se debe aplicar la regla de negocio R.N.10.

#### 4.1.2. Reglas de negocio 

##### R.N.01. Email único

No pueden existir dos usuarios registrados con el mismo email.

**Prueba de aceptación**
- Se registra un usuario con el email ana@correo.com y no se recibe ningún error.
- Se intenta registrar otro usuario con el email ana@correo.com y se recibe un error de email ya registrado.

##### R.N.02. Saldo no negativo

El saldo de una cuenta nunca puede ser menor que 0, ni al crearla ni después de registrar un gasto o una transferencia. Un gasto puede dejar el saldo justo en 0.

**Prueba de aceptación**
- Se intenta crear una cuenta con saldo inicial de -50 € y se recibe un error.
- Con un saldo de 1500 €, se registra un gasto de 1500 € y el saldo queda en 0 € sin ningún error.
- Con un saldo de 1500 €, se intenta registrar un gasto de 2000 € y se rechaza por saldo insuficiente.

##### R.N.03. Importes positivos

Los importes de los movimientos, transferencias y presupuestos tienen que ser siempre mayores que 0. Si un movimiento es un ingreso o un gasto lo indica su tipo, no el signo del importe.

**Prueba de aceptación**
- Se intenta registrar un ingreso de -100 € y se recibe un error.
- Se intenta registrar un gasto de 0 € y se recibe un error.
- Se intenta crear un presupuesto de -300 € y se recibe un error.

##### R.N.04. Actualización del saldo

Al registrar un movimiento, el saldo de la cuenta se actualiza automáticamente: los ingresos se suman y los gastos se restan. Si se elimina un movimiento, se deshace su efecto en el saldo.

**Prueba de aceptación**
- Una cuenta tiene 1000 €, se registra un gasto de 500 € y un ingreso de 300 €, y al consultar la cuenta el saldo es de 800 €.
- Se elimina el gasto de 500 € anterior y el saldo vuelve a ser de 1300 €.

##### R.N.05. Clasificación de los movimientos

Todo movimiento tiene que ser de tipo ingreso o gasto, y su categoría tiene que ser del mismo tipo. Si no se indica categoría, se asigna automáticamente "Otros gastos" u "Otros ingresos" según el tipo.

**Prueba de aceptación**
- Se intenta registrar un movimiento sin tipo y se rechaza, sin que cambie el saldo de la cuenta.
- Se intenta registrar un gasto con la categoría "Nómina" (de ingreso) y se recibe un error.
- Se registra un gasto sin indicar categoría y se guarda en "Otros gastos".
- Se registra un ingreso sin indicar categoría y se guarda en "Otros ingresos".

##### R.N.06. Condiciones de las transferencias

Una transferencia solo se puede hacer desde una cuenta del propio usuario, hacia una cuenta distinta, con la misma moneda y con un importe que no supere el saldo de la cuenta de origen. La transferencia es interna si las dos cuentas son del mismo usuario y externa si no lo son.

**Prueba de aceptación**
- Con A = 500 € y B = 1000 €, se transfieren 200 € de A a B y los saldos quedan en A = 300 € y B = 1200 €.
- Con A = 500 € y B = 1000 €, se intentan transferir 700 € de A a B y se rechaza por saldo insuficiente; los saldos no cambian.
- Se intenta hacer una transferencia de la cuenta A a la propia cuenta A y se recibe un error.
- Se intenta transferir desde una cuenta en EUR a una cuenta en USD y se recibe un error.
- Un usuario intenta hacer una transferencia desde una cuenta que no es suya y se rechaza.

##### R.N.07. Cuentas inactivas

Una cuenta con movimientos no se puede eliminar, solo desactivar, para no perder su historial. En una cuenta inactiva no se pueden registrar movimientos ni transferencias.

**Prueba de aceptación**
- Se intenta registrar un gasto en una cuenta inactiva y se recibe un error.
- Se intenta hacer una transferencia hacia una cuenta inactiva y se recibe un error.
- Se intenta eliminar una cuenta que tiene movimientos y se recibe un error indicando que debe desactivarse.

##### R.N.08. Gestión de categorías

Las categorías generales solo las puede crear un administrador, y están disponibles para todos los clientes. Cada cliente puede crear categorías personales, que solo ve él. Un usuario no puede tener dos categorías con el mismo nombre, contando las generales y las suyas.

**Prueba de aceptación**
- El administrador crea la categoría general "Ocio" y no se recibe ningún error.
- El administrador intenta crear otra categoría general "Ocio" y se recibe un error.
- Un cliente intenta crear una categoría general y se rechaza por no tener permisos.
- Un cliente intenta crear una categoría personal llamada "Ocio", que ya existe como general, y se recibe un error.
- Dos clientes distintos crean cada uno una categoría personal llamada "Mascota" y no se recibe ningún error.

##### R.N.09. Un presupuesto por categoría y mes

Cada usuario solo puede tener un presupuesto por categoría en un mismo mes y año.

**Prueba de aceptación**
- Existe un presupuesto de 300 € para "Vivienda" en marzo de 2026; se intenta crear otro para "Vivienda" en marzo de 2026 y se rechaza.
- Existe un presupuesto para "Ocio" en abril de 2026; se crea otro para "Ocio" en mayo de 2026 y no se recibe ningún error.
- Dos usuarios distintos crean un presupuesto para "Ocio" en abril de 2026 y no se recibe ningún error.

##### R.N.10. Solo se presupuestan gastos

Solo se pueden crear presupuestos para categorías de tipo gasto.

**Prueba de aceptación**
- Se crea un presupuesto para la categoría "Transporte" (de gasto) y no se recibe ningún error.
- Se intenta crear un presupuesto para la categoría "Nómina" (de ingreso) y se rechaza.

##### R.N.11. Cálculo del gasto real

El gasto real de un presupuesto es la suma de todos los gastos del usuario en esa categoría durante ese mes. Las transferencias internas entre cuentas del mismo usuario no cuentan como gasto.

**Prueba de aceptación**
- Con un presupuesto de 1000 € para "Alimentación" en marzo, se registran gastos de 150 € y 200 € en esa categoría en marzo; el gasto real es de 350 € y quedan 650 €.
- Se registra un gasto de "Alimentación" en abril y no cambia el gasto real del presupuesto de marzo.
- Se hace una transferencia interna de 500 € de la cuenta corriente a la de ahorro y el gasto real de los presupuestos no cambia.

### 4.2. Mapa de historias de usuario

En el mapa se organizan las historias de usuario debajo del requisito general al que pertenecen.

| R.G.01. Gestionar las cuentas | R.G.02. Controlar ingresos y gastos | R.G.03. Mover dinero entre cuentas | R.G.04. Planificar con presupuestos | R.G.05. Analizar la situación económica | R.G.06. Mantener el sistema |
|:---|:---|:---|:---|:---|:---|
| R.I.02. Cuentas | R.I.03. Movimientos | R.I.05. Transferencias | R.I.06. Presupuestos | R.F.03. Resumen mensual | R.I.01. Usuario |
| R.F.01. Listado de cuentas y saldo total | R.I.04. Categorías | R.F.07. Historial de transferencias | R.F.05. Seguimiento de presupuestos | R.F.04. Gasto por categorías | R.F.09. Listado de usuarios |
|  | R.F.02. Consulta de movimientos por fechas |  | R.F.06. Presupuestos superados | R.F.08. Evolución del gasto de una categoría |  |

### 4.3. Requisitos no funcionales

##### R.N.F.01. Privacidad de los datos
Como cliente, quiero que solo yo pueda ver mis saldos, movimientos y presupuestos, incluido el administrador, para que mis datos económicos sean privados, como exige la Ley de Protección de Datos.

##### R.N.F.02. Contraseñas protegidas
Como administrador, quiero que las contraseñas no se guarden en texto plano, sino cifradas mediante una función hash, para que no se puedan leer aunque alguien acceda a la base de datos.

##### R.N.F.03. Operaciones completas
Como cliente, quiero que una transferencia se haga entera o no se haga (si se resta el dinero de una cuenta, tiene que sumarse en la otra), para que nunca desaparezca ni aparezca dinero por un fallo a mitad de la operación. Del mismo modo, si se registran dos movimientos a la vez sobre la misma cuenta, ninguno de los dos debe perderse al actualizar el saldo.


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


