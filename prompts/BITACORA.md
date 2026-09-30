# Bitacora de tecnicas avanzadas

Laboratorio 07: Tecnicas Avanzadas de Prompting.
Herramienta de IA usada: (escribe aqui cual usaste)

## Ejercicio 2: Zero-shot, one-shot y few-shot

| Tipo      | Aciertos (de 5) | Formato de la respuesta                                                            | Todas con el mismo formato (Si/No) |
| --------- | --------------- | ---------------------------------------------------------------------------------- | ---------------------------------- |
| Zero-shot | 5               | Tabla estructurada (N.°, Comentario, Clasificación) con viñetas de color y resumen | Sí                                 |
| One-shot  | 5               | Lista numerada con el formato `Número. Comentario -> Etiqueta`                     | Sí                                 |
| Few-shot  | 5               | Líneas de texto entre comillas con flecha y etiqueta (`"Comentario" -> Etiqueta`)  | Sí                                 |

## Ejercicio 3: Chain of Thought

| Pedido      | Respuesta de la IA                                                                    | Muestra los pasos (Si/No) | Correcta (Si/No) |
| ----------- | ------------------------------------------------------------------------------------- | ------------------------- | ---------------- |
| Directo     | 318.60                                                                                | No                        | Sí               |
| Paso a paso | Desarrollo detallado mostrando los cálculos del descuento, IGV y multiplicación final | Sí                        | Sí               |

Es útil porque permite verificar cada operación matemática de forma independiente y detectar exactamente en qué paso exacto se cometería un error si el resultado final fuera incorrecto.

## Ejercicio 4: Role prompting

| Version        | Vocabulario (sencillo/tecnico)                         | Usa ejemplos o codigo                             | A quien le sirve mas                              |
| -------------- | ------------------------------------------------------ | ------------------------------------------------- | ------------------------------------------------- |
| A. Sin rol     | Sencillo y directo                                     | Sí (código en Python y analogía de caja)          | A cualquier usuario que busca una consulta rápida |
| B. Rol docente | Muy sencillo y didáctico                               | Sí (código en Python y explicaciones paso a paso) | A estudiantes que nunca han programado            |
| C. Rol senior  | Técnico (enfocado en memoria y tipos de datos en Java) | Sí (código en Java con tipado estricto)           | A compañeros de trabajo o programadores           |

## Ejercicio 5: Descomposicion

- **Paso 1:** La IA entregó una lista estructurada con los 5 requisitos principales del sistema de inventario (Registro de productos, Control de stock, Búsqueda de productos, Registro de ventas y Reportes de inventario).
- **Paso 2:** La IA diseñó 5 clases necesarias (`Producto`, `Inventario`, `Venta`, `DetalleVenta` y `Reporte`) especificando los atributos con sus respectivos tipos de datos y la relación entre ellas.
- **Paso 3:** La IA escribió el código completo en Java de la clase `Producto` con sus atributos privados (`codigo`, `nombre`, `precio`, `stock`), constructor, métodos getters y setters.
- **Paso 4:** La IA revisó el código de la clase `Producto` y propuso 3 mejoras concretas: validar que el precio y el stock no sean negativos, validar que los datos no estén vacíos y agregar el método `toString()`.
- **Comparación con el pedido de una sola vez:** Hacerlo por pasos permitió estructurar el sistema de forma ordenada, obteniendo primero los requisitos y el diseño de clases antes de escribir el código. Un pedido de una sola vez habría generado una respuesta mucho más general o caótica sin permitirnos verificar la arquitectura del software paso a paso.

## Ejercicio 6: Prompt estructurado y autocritica

| Qué revisar                                      | Cumple (Sí / No) |
| :----------------------------------------------- | :--------------- |
| ¿Tiene las 4 columnas pedidas?                   | Sí               |
| ¿Incluye el bloqueo después de 3 intentos?       | Sí               |
| ¿Incluye casos con campos vacíos?                | Sí               |
| ¿Indica qué casos agregó en la autocrítica?      | Sí               |
| ¿Hay algún caso repetido o que no tenga sentido? | No               |

```text
Prompt estructurado
<rol>Actua como analista de pruebas de software.</rol>
<contexto>Login web con correo y contrasena. La cuenta se bloquea
despues de 3 intentos fallidos.</contexto>
<tarea>Piensa paso a paso que puede fallar y escribe 6 casos de prueba.</tarea>
<formato>Tabla con las columnas: ID, escenario, datos de entrada,
resultado esperado.</formato>

Mensaje de autocritica
...(Agrego y corrigio algunos casos)...
Casos que agregué
TC-07: ambos campos vacíos.
TC-08: correo sin @ / formato inválido.
TC-09: contraseña con espacios.
TC-10: correo vacío.
TC-11: contraseña vacía.

Además, el TC-09 es importante porque hay que distinguir entre espacios permitidos como parte de la contraseña y espacios introducidos accidentalmente. La regla exacta debería estar definida en los requisitos del sistema.
```
