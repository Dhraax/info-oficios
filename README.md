# Plan de pruebas de Oficios

Este documento te explica cómo funciona el sistema de oficios, qué
tienes que probar en el tuyo y qué necesitamos que nos cuentes cuando algo no
cuadre.

Léelo entero una vez antes de empezar. Después usa la sección de tu oficio como
guía y vuelve a la sección 1 siempre que dudes.

---

## 0. Antes de empezar

### Cómo se fabrica, paso a paso

1. Acércate a la mesa de tu oficio y úsala.
2. Elige una **categoría** (por ejemplo, "Escudos").
3. Elige una **receta**. El menú te dice qué materiales pide, qué dificultad
   tiene y cuánto oro cuesta.
4. Introduce los materiales que vas a necesitar para la receta y vuelve al menu para seleccionarla.
5. Confirmala, el personaje hace una **tirada**: si supera la dificultad, el
   objeto aparece en tu inventario; si no, has fallado y pierdes los materiales.

Eso es todo. El resto del documento son los detalles de cada paso.

### De dónde salen los materiales

Hay 110 materiales que ningún oficio fabrica y que tienes que conseguir por tu
cuenta. **Los 110 están disponibles**, repartidos en dos sitios que no se
solapan:

| Dónde | Cuántos | Qué encontrarás |
|---|---:|---|
| **Cofres** del **área de oficios** | 74 | lo que se recolecta (pepitas, pieles, troncos, hierbas, gemas en bruto) y lo que sale de procesarlo (lingotes, cueros curtidos, tablones, gemas talladas) |
| **Tiendas de oficio** del **área de tiendas** | 36 | lo que se compra: moldes, plantillas, kits, agujas, sedas, correas, tachones, sal, tanino, aceite de herrería, botellas, accesorios de carpintería y cilindros |

La regla es sencilla: **la materia prima la coges del cofre y el resto lo
compras**. Si buscas algo en el cofre y no está, no es un fallo: es que se
compra en la tienda. Si no lo encuentras ni en la tienda, ni fabricandolo o en los cofres, es que es un fallo.

### Lo que todavía no existe

**No se puede recolectar nada del mundo.** No hay vetas que picar ni plantas
que recoger: los materiales en bruto salen del cofre.

### Uso del oro

Cada intento te cobra el "Valor total" que muestra la receta, **aciertes o
falles**. Sumado a lo que tienes que comprar en las tiendas, vas a necesitar
bastante. Empiezas con 30k, si ves que necesitas mas, crea otro personaje y subele niveles con las palancas a los lados de cada mesa.

---

## 1. Lo que tienes que probar en todos los oficios

Da igual qué oficio te haya tocado: estas reglas son iguales para todos, y es
donde más probable es que encuentres un fallo. Compruébalas todas en tu oficio.

### 1.1 Herramientas

Cada mesa te pide llevar una herramienta, y hay dos formas de llevarla:

- **Equipada**: puesta en el personaje, no basta con tenerla en la mochila.
- **En el inventario**: basta con llevarla encima.

| Estación | Herramienta | Cómo llevarla |
|---|---|---|
| Yunque | **Martillo ligero de herrero** | **equipada** |
| Forja | **Guantes de Fundidor** | equipada |
| Mesa de alquimia | **Guantes de Alquimista** | equipada |
| Caldero | **Guantes de Cocinero** | equipada |
| Mesa de peletero | **Aguja** (o **Aguja grande**) equipada + **Kit de herramientas para trabajar el cuero** en el inventario |
| Mesa de sastrería | **Aguja** (o **Aguja grande**) equipada + **Kit de herramientas del Sastre** en el inventario |
| Banco de carpintero | **Kit de herramientas del carpintero** en el inventario |
| Tabla de serrería | **Kit de herramientas del serrador** + **Sierra del serrador** en el inventario |
| Mesa de joyero | **Kit de herramientas de Orfebre** en el inventario, **sólo para tallar gemas** |
| Tina de curtido | **ninguna** |

Prueba esto:

1. Intenta fabricar **sin la herramienta**. Debe negarse, y el mensaje tiene que
   decirte el **nombre** del objeto que te falta. Si te suelta un código raro en
   vez de un nombre, repórtalo.
2. Cuando la herramienta se pide **equipada**, prueba a llevarla sólo en la
   mochila. También debe negarse.
3. En la mesa de joyero, tallar una gema pide el kit pero **engarzarla no**.
   Saca el kit del inventario y prueba las dos cosas: tallar debe negarse,
   engarzar debe dejarte.
4. **Las herramientas se rompen.** Cada intento tiene un 10% de romper la que
   llevas. Cuando se rompa, el intento se cancela y **no debes perder ningún
   material**. Si pierdes materiales al romperse la herramienta, es un fallo.

### 1.2 Materiales, moldes y plantillas

Un molde o una plantilla no es un material: es la pieza que da forma al objeto,
y por eso se comporta distinto.

- **Si aciertas**, gastas los materiales **y también el molde o la plantilla**.
- **Si fallas**, pierdes los materiales pero **el molde o la plantilla se
  queda**.
- En Alquimia, la botella funciona igual que un molde.

Prueba las dos ramas por separado y **cuenta el inventario antes y después**.

### 1.3 Oro

- El "Valor total" se te cobra **al empezar el intento**, no al acertar.
- Si no tienes oro suficiente, debe cancelarse antes de tocar tus materiales.
- **Fallar te cuesta el oro igual.** No se devuelve, y eso es lo previsto.

### 1.4 Experiencia y nivel

- Acertar te da la experiencia completa de la receta. Fallar te da el 12%.
- Al llegar a **nivel 20** dejas de ganar experiencia y el mensaje te dirá que
  ya dominas el oficio. Comprueba que el número **no sigue subiendo**.
- **Sólo puedes tener dos oficios a nivel 2 o más.** Alquimia es la excepción y
  no ocupa plaza. Prueba a subir un tercer oficio de nivel 1 a nivel 2: debe
  negarse con un aviso, y no debes seguir ganando experiencia en él.

### 1.5 Qué recetas ves en el menú

El menú te muestra sólo lo que tu nivel te permite fabricar, y se va abriendo
poco a poco según subes:

| Estación | A nivel 1 | A nivel 5 | Total del oficio |
|---|---:|---:|---:|
| Yunque | 8 | 32 | 120 |
| Mesa de joyero | 6 | 27 | 90 |
| Banco de carpintero | 10 | 20 | 78 |
| Mesa de peletero | 7 | 21 | 70 |
| Mesa de alquimia | 2 | 16 | 65 |
| Mesa de sastrería | 3 | 9 | 30 |
| Forja | 1 | 4 | 15 |
| Tina de curtido | 1 | 3 | 10 |
| Caldero | 1 | 2 | 8 |
| Tabla de serrería | 1 | 2 | 8 |

Hay un ajuste para ver **también** las recetas por encima de tu nivel:

1. Usa la **Herramienta de Jugador de PDB** (la misma con la que disipas o te
   cambias el retrato).
2. Entra en el **libro de oficios**. Ahí ves tu nivel en cada oficio.
3. Abajo del todo tienes un **activador** que muestra todas las recetas aunque
   estén por encima de tu nivel.

Con el activador **encendido** se ven todas, y eso es intencionado: no lo
reportes. Los números de la tabla de arriba son con el activador **apagado**,
que es como tienes que probar el filtrado.

### 1.6 El objeto que sale

Cuando aciertes, revisa el objeto que aparece en tu inventario:

- Sale **identificado** (ves sus propiedades sin tener que identificarlo).
- Sale **marcado como robado**.
- Su **nombre** coincide con el de la receta que usaste.
- Sus propiedades son **exactamente** las que anunciaba la receta, ni una más
  ni una menos.

Vas a recibir aparte las recetas de tu oficio en un excel. **Tu trabajo
es compararlas**: lo que dice la planilla tiene que ser lo que trae el objeto,
propiedad por propiedad. Si no coincide, es justo el tipo de fallo que buscamos.

### 1.7 La tirada

Al fabricar verás un mensaje con la tirada desglosada:

```
Tirada: 12 + 20 (oficio) + 0 (ayuda) = 32 contra DC 33
```

Se lee así: el dado sacó 12, tu oficio suma 20, la ayuda por características
suma 0, y el total de 32 no llega al 33 que pedía la receta. Ese intento falla.

Un **1 natural siempre falla** y un **20 natural siempre acierta**, pase lo que
pase con la dificultad.

**Que la "ayuda" salga 0 es normal** con características medias: hacen falta 14
en las dos características del oficio, o 10 rangos de Artesanía, para que sume
aunque sea 1. No lo reportes.

---

## 2. Herrería

**Mesas:** Forja (15 recetas) y Yunque (120).

La forja convierte pepitas en lingotes y el yunque convierte lingotes en
objetos, así que tienes que probar en ese orden.

1. **Forja.** Tres pepitas del mismo metal más una **Pepita de carbón** te dan
   un lingote. Comprueba que el carbón se gasta y que sin él no te deja
   fabricar.
2. **Aceroscuro.** Sus **9 recetas** (el lingote y los 8 objetos) piden además
   **Aceite de Herrería**. Comprueba que sin aceite no te dejan.
3. **Yunque.** Ocho familias: espadas largas, munición, yelmos, escudos
   pequeños, escudos grandes, paveses, cotas de escamas y armaduras completas.
   Cada familia tiene su propio molde. Fabrica al menos una de cada.
4. **Los 15 metales.** Del cobre a la adamantita. Comprueba que las propiedades
   del objeto mejoran conforme subes de metal.

**Ten en cuenta:** de momento las espadas largas son las únicas armas que se
pueden fabricar. Que no estén las demás no es un fallo.

---

## 3. Joyería

**Mesa:** Mesa de joyero (90 recetas). No depende de ningún otro oficio: todo se
hace en la misma mesa.

Son tres pasos, en este orden:

1. **Aros y cadenas** (6 recetas). Un cilindro tratado más su molde. Hay de
   cobre, oro y platino.
2. **Tallado** (28 recetas). Una piedra en bruto se convierte en gema tallada.
   **Este paso pide el kit.** Ocho de las 28 sueltan además una **arenilla**:
   comprueba que te llegan **los dos objetos**, no sólo la gema.
3. **Engarce** (56 recetas). Un aro o una cadena más una gema tallada te dan la
   pieza terminada.

Mira con lupa estas cuatro cosas:

- **El metal es sólo estético.** Los aros y las cadenas salen vacíos, sin
  propiedades: todo lo que tenga el anillo o el amuleto se lo pone la gema. El
  metal sólo marca en qué escalón del oficio estás.
- **Las propiedades de las gemas** son lo más delicado del sistema, y diez de
  ellas dan **huecos de conjuro**. Tienen sección propia justo debajo.
- **Las cinco inmunidades** tienen que dar exactamente **20%**: Ópalo de fuego
  (fuego), Corvidar (ácido), Beljuril (eléctrico), Orlo (frío) y Rubí
  (cortante).
- **Una pieza ya engarzada no puede usarse como material.** Prueba a meter un
  anillo terminado en otra receta: no debe aceptarlo.

### Las diez gemas de conjuros

Un **hueco de conjuro** es un lanzamiento extra al día, de un nivel concreto y
para una clase concreta. Si un anillo da "Clérigo, nivel 4, 2 huecos", un
clérigo que lo lleve puede lanzar dos conjuros más de nivel 4 cada día. A quien
no sea clérigo, ese anillo no le da nada.

Cada una de estas gemas tiene **anillo y amuleto**, y los dos dan exactamente lo
mismo. Esta es la lista completa de lo que debe salir:

| Gema | Metal | Clase | Nivel de conjuro | Cuántos huecos |
|---|---|---|---:|---:|
| Jade de tumba | cobre | Bardo | 2 | 2 |
| Piedra pícara | cobre | Bardo | 3 | 1 |
| Piedra pícara | cobre | Bardo | 4 | 1 |
| Lágrima roja | cobre | Druida | 4 | 2 |
| Ópalo | cobre | Hechicero | 4 | 2 |
| Ópalo negro | oro | Clérigo | 4 | 2 |
| Orblen | oro | Mago | 4 | 2 |
| Jacinto | platino | Druida | 6 | 2 |
| Esmeralda | platino | Hechicero | 6 | 2 |
| Zafiro negro | platino | Clérigo | 6 | 2 |
| Amarazha | platino | Mago | 6 | 2 |

**La piedra pícara es la única con dos filas**: una sola pieza da un hueco de
nivel 3 **y** un hueco de nivel 4. Las demás dan dos huecos del mismo nivel.

Fabrica la pieza y **lee su descripción**. Tiene que nombrar la clase y el
nivel que dice la tabla. Dos huecos significa que la propiedad se aplica dos
veces, así que la verás repetida o contada como 2; lo que no puede pasar es que
salga una sola vez.

Comprueba las once filas. La clase y el nivel del conjuro son lo que hay que
mirar con más cuidado de todo el oficio.

---

## 4. Peletería

**Mesas:** Tina de curtido (10 recetas) y Mesa de peletero (70).

1. **Tina.** Piel en bruto más sal y tanino te dan cuero curtido. **Es la única
   mesa que no pide herramienta**: comprueba que efectivamente te deja fabricar
   sin llevar nada.
2. **Mesa.** Siete familias: cuatro clases de armadura, botas, cinturones y
   guantes de monje. Cada una con su plantilla. Fabrica al menos una de cada.
3. **Diez pieles**, desde roedor hasta dragón. Las de dragón son las de arriba
   del todo.
4. Cada escalón pide **un cuero más** que el anterior: comprueba que la
   cantidad sube conforme avanzas.

---

## 5. Sastrería

**Mesa:** Mesa de sastrería (30 recetas).

Sastrería usa las mismas pieles que Peletería pero **sube con su propio nivel**,
y ése es el punto principal a verificar: subir Sastrería no debe subir
Peletería, ni al revés. Compruébalo mirando tu libro de oficios antes y después
de fabricar unas cuantas piezas.

1. Tres familias: ropas, brazales y capas.
2. Todas piden **2 sedas finas** además del cuero, y las sedas **se gastan
   siempre**, aciertes o falles.
3. La aguja va **equipada** y el kit propio (**Kit de herramientas del Sastre**)
   en el inventario. Si la mesa te pide el kit de peletero, es un fallo.

---

## 6. Carpintería

**Mesas:** Tabla de serrería (8 recetas) y Banco de carpintero (78).

1. **Serrería.** 3 troncos más las herramientas te dan 1 tablón. Hay ocho
   maderas.
2. **Banco.** Diez familias: arcos cortos, arcos largos, ballestas ligeras,
   ballestas pesadas, bastones, clavas, escudos pequeños, escudos grandes,
   flechas y virotes.

**Esto es lo más importante de tu oficio:** fabrica uno de cada y **lee la
descripción del objeto** para confirmar que trae la propiedad que le toca.

| Propiedad | En qué objetos | Recetas |
|---|---|---:|
| Críticos masivos | arcos y ballestas | 22 |
| Bono de ataque | arcos y ballestas | 16 |
| Poderoso | arcos y ballestas | 12 |
| Ralentizar al golpear | flechas y virotes | 6 |

Si alguna no aparece en la descripción, es un fallo. Di siempre **qué madera
y qué objeto** era.

---

## 7. Alquimia

**Mesas:** Caldero de hierbas (8 recetas) y Mesa de alquimia (65).

Alquimia es la excepción del sistema: **no ocupa plaza de oficio**, así que
cualquiera puede subirla aunque ya tenga otros dos.

1. **Caldero.** Ocho hierbas base a partir de los ingredientes recogidos.
2. **Mesa.** 65 pociones y venenos. Cada una consume una **botella**, que se te
   queda si fallas.
3. **Bébete lo que fabricas.** La poción tiene que hacer su efecto. Prueba una
   de cada tipo, no sólo las primeras.
4. Dos casos que **no deben hacer nada** al beberlos, y está bien así: *Agua
   pura* y la *Galleta mágica*.

---

## 8. Qué NO es un fallo

Para que no gastes tiempo reportando cosas que ya sabemos:

- **La "ayuda" de la tirada sale 0** con características normales.
- **Fallar te cuesta el oro y los materiales.** Sólo se salva el molde o la
  plantilla.
- **No se puede recolectar** minerales, plantas ni pieles. Los materiales en
  bruto salen del cofre.
- **Que algo no esté en el cofre.** Los moldes, plantillas, kits, sedas,
  aceites, botellas, accesorios y cilindros **se compran** en las tiendas de
  oficio. El cofre sólo tiene materiales en bruto y lo que sale de procesarlos.
- **Que no existan aros de plata.** La plata ya no se usa en joyería. Ahora
  bien, si te aparece una pieza con "plata" en el nombre, **eso sí es un fallo**
  y queremos saberlo.
- **Que la tina de curtido no pida herramienta.** Es la única mesa así.
  Confírmalo, pero no lo reportes.

---

## 9. Cómo reportar un fallo

Un fallo sólo sirve si podemos repetirlo. Cuéntanoslo con esto:

1. **Oficio, mesa y el nivel que tenías** en ese momento.
2. **Nombre exacto de la receta** y el **número de ID** que muestra el menú.
3. **Qué esperabas que pasara y qué pasó en realidad.**
4. **El mensaje completo de la tirada**, copiado tal cual.
5. Si el problema es de propiedades: **la descripción del objeto**, copiada
   entera.
6. Una captura, si el problema se ve en pantalla.

Cuando un objeto salga con **el nombre, la dificultad o las propiedades
equivocadas**, dinos siempre el **ID de la receta**.
