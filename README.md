# Guía de oficios

## Usar una estación

1. Usa la estación. Primero se abrirá su inventario.
2. Deposita los componentes de la receta y cierra el inventario.
3. En el menú, entra en la categoría correspondiente y elige la receta.
4. Si la receta admite varios resultados, elige cuál quieres fabricar.
5. Comprueba el resultado, los componentes, la DC y el coste. Las tablas de
   esta guía también muestran el nivel mínimo y la experiencia.
6. Confirma el intento. Al pulsar, se vuelven a comprobar el nivel, la
   herramienta, los componentes y el oro.

Desde el propio menú puedes volver a abrir el inventario sin perder la receta
seleccionada. Retira lo que no hayas usado antes de alejarte de la estación.

## Cómo leer una receta

| Dato | Significado |
|---|---|
| **Nivel** | Nivel mínimo del oficio necesario para intentarla |
| **DC** | Dificultad que debe alcanzar la tirada |
| **XP** | Experiencia del oficio recibida al acertar |
| **Oro** | Coste del intento; también se paga si la tirada falla |
| `*` | Componente de forma, como un molde, plantilla o botella: se conserva al fallar y se consume al acertar |
| `[elige]` | La receta abre una selección adicional para escoger el producto final |
| `×N` en el resultado | Cantidad de unidades que entrega la receta |
| `+` en el resultado | La receta entrega además un segundo objeto |

El menú oculta las recetas que superan tu nivel. El libro de oficios de la
Herramienta de Jugador de PDB permite mostrarlas para consultarlas, pero no
elimina el requisito de nivel.

## Componentes y suministros

Las tablas indican qué hay que depositar, no dónde se consigue cada objeto. Los
recursos en bruto pueden proceder de la recolección, el botín u otros sistemas;
los materiales intermedios se procesan en estaciones y los suministros se
compran en sus tiendas. La ficha de la receta muestra el nombre y la cantidad
exactos de cada componente.

Los componentes marcados con `*` se tratan de forma especial. Si la tirada
falla, se pierden los demás componentes, pero esos objetos se conservan. Si la
tirada acierta, se consume todo lo indicado.

## Herramientas

**Equipada** significa que la herramienta debe estar puesta; no basta con
llevarla en la mochila. **Inventario** significa que sólo hay que llevarla
encima.

| Estación | Herramienta | Dónde llevarla |
|---|---|---|
| Yunque de herrero | Martillo ligero de herrero | equipada |
| Forja | Guantes de Fundidor | equipada |
| Mesa de alquimia | Guantes de Alquimista | equipada |
| Caldero de hierbas | Guantes de Cocinero | equipada |
| Mesa de peletero | Aguja o Aguja grande; Kit de herramientas para trabajar el cuero | aguja equipada; kit en el inventario |
| Mesa de sastrería | Aguja o Aguja grande; Kit de herramientas del Sastre | aguja equipada; kit en el inventario |
| Banco de carpintero | Kit de herramientas del carpintero | inventario |
| Tabla de serrería | Kit de herramientas del serrador; Sierra del serrador | inventario |
| Mesa de joyero | Kit de herramientas de Orfebre | inventario; sólo al tallar gemas |
| Tina de curtido | ninguna | - |

Las herramientas pueden romperse al comenzar un intento. Si ocurre, el
intento se cancela antes de cobrar oro o consumir componentes.

## Tirada, resultado y progreso

Cada intento tira `d20` y suma el nivel del oficio y la ayuda aplicable. El
mensaje muestra el desglose y la DC. Un 1 natural siempre falla y un 20 natural
siempre acierta.

Al acertar, el producto llega identificado y con las propiedades definidas por
la receta. Al fallar, no se crea el producto: se conservan sólo los
componentes marcados con `*`, y se recibe una parte de la experiencia indicada.

El progreso es independiente para cada oficio. Un personaje puede desarrollar
dos oficios de fabricación por encima del nivel inicial; Alquimia no ocupa una
de esas plazas.

## Comprobar las propiedades

Durante la etapa de pruebas, las tablas de cada oficio en esta guía son la
referencia de las propiedades esperadas. Fabrica una receta y compara la
descripción completa del objeto con su tabla. El nombre y las propiedades deben
coincidir, sin que sobre o falte ninguna.

En las armas, las propiedades las determina el material: todas las armas de
acero, por ejemplo, deben recibir las propiedades asignadas al acero. El tipo
de arma sólo puede cambiar el daño físico complementario que le corresponda.
En Alquimia también se comprueban los efectos de todas las pociones y venenos;
la tabla de referencia está en la [guía de Alquimia](alquimia/README.md).

## Recetas por oficio

- [Alquimia](alquimia/README.md)
- [Arcano](arcano/README.md)
- [Carpintería](carpinteria/README.md)
- [Herrería](herreria/README.md)
- [Joyería](joyeria/README.md)
- [Peletería](peleteria/README.md)
- [Sastrería](sastreria/README.md)
