# Tarea: Mi prompt avanzado

## Tarea elegida

Diseñar las clases y atributos en Java para un sistema de inventario de una bodega (tienda pequeña), asegurando una correcta aplicación de los principios de Programación Orientada a Objetos (POO) como encapsulamiento, constructores y relaciones entre clases.

## Version 1: prompt basico

```text
Crea las clases para un sistema de inventario de una bodega en Java con sus atributos.
```

## Version 2

```text
<rol>Actúa como un desarrollador de software senior especializado en backend con Java y POO.</rol>
<tarea>Diseña las clases necesarias para un sistema de inventario de una bodega (como Producto, Categoria, Proveedor e Inventario) indicando los atributos con sus tipos de dato y encapsulamiento.</tarea>
```

## Version 3: prompt final

La versión final se divide en dos partes (dos mensajes enviados de forma sucesiva en el mismo chat), ya que la autocrítica requiere obligatoriamente que la IA haya generado una respuesta previa para poder evaluarla y corregirla en el siguiente turno.

Mensaje 1 (Prompt estructurado con Chain of Thought):

```text
<rol>Actúa como un desarrollador de software senior especializado en backend con Java y POO.</rol>
<contexto>Estamos desarrollando un módulo de gestión de stock para una bodega pequeña, donde es fundamental controlar los productos, sus precios, stock mínimo y relaciones con categorías y proveedores.</contexto>
<tarea>Piensa paso a paso qué clases se necesitan, cómo se relacionan entre sí y cuáles son sus atributos y métodos principales. Luego, genera el diseño técnico completo.</tarea>
<formato>Escribe la respuesta estructurada por clases, detallando para cada una sus atributos (con su visibilidad y tipo de dato) y métodos esenciales.</formato>
```

Mensaje 2 (Mensaje de Autocrítica en el mismo chat):

```text
Revisa el diseño de clases que acabas de generar: evalúa si falta alguna validación importante en los atributos (como evitar precios o stock negativos) o si alguna relación entre clases puede generar problemas de consistencia. Agrega las correcciones necesarias e indica explícitamente qué mejoraste.
```

## Tecnicas usadas en el prompt final

| Técnica                 | Parte del prompt final donde se aplica                                                   | Qué aporta al resultado                                                                                                    |
| :---------------------- | :--------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------- |
| **Prompt Estructurado** | Uso de etiquetas `<rol>`, `<contexto>`, `<tarea>` y `<formato>` en el primer mensaje     | Ordena las instrucciones claramente para que la IA no mezcle el contexto con los requerimientos.                           |
| **Chain of Thought**    | "Piensa paso a paso qué clases se necesitan, cómo se relacionan..." en el primer mensaje | Obliga a la IA a razonar la arquitectura antes de dar la respuesta final en lugar de generar código al azar.               |
| **Autocrítica**         | Enviado en el segundo mensaje ("Revisa el diseño de clases que acabas de generar...")    | Permite que la IA evalúe su propio diseño ya escrito en busca de fallos de validación o consistencia que se hayan omitido. |

## Evaluacion del resultado

| Qué revisar                                                              | Cumple (Sí / No) |
| :----------------------------------------------------------------------- | :--------------- |
| ¿El rol definido es específico y técnico?                                | Sí               |
| ¿Incluye las clases necesarias para una bodega (Producto, Stock, etc.)?  | Sí               |
| ¿Razona el diseño paso a paso (Chain of Thought)?                        | Sí               |
| ¿Se aplica la autocrítica en un mensaje posterior dentro del mismo chat? | Sí               |

## Por que elegi estas tecnicas

Elegí el Prompt Estructurado porque permite separar de forma limpia el rol, el contexto de negocio (una bodega), la tarea y el formato deseado, evitando ambigüedades desde el inicio. Incorporé Chain of Thought porque diseñar arquitectura de clases requiere un análisis lógico previo de las relaciones entre entidades antes de definir atributos. Dividí la Autocrítica en un segundo mensaje porque esta técnica no puede ir aglutinada en el prompt inicial; conceptualmente y de manera operativa, la IA necesita generar un resultado primero para que luego, mediante un nuevo estímulo en la misma ventana de contexto, pueda analizarlo críticamente y corregir sus propias deficiencias (como faltas de validación en precios o stock). Descarté técnicas como few-shot (ejemplos) porque limitaban la libertad de diseño orientado a objetos.
