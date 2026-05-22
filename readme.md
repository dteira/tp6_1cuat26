<center>
    <h1>Programación 2</h1>
    <h3>Práctica 4: Árboles binarios</h3>
    <h5>1er cuatrimestre 2026</h5>
</center>

---

## Objetivos de la práctica

- Comprender la estructura y propiedades de los árboles binarios.
- Construir y analizar Árboles Binarios de Búsqueda (ABB).
- Aplicar recorridos clásicos: inorder, preorder y postorder.
- Analizar la complejidad temporal de las operaciones sobre árboles.
- Implementar árboles balanceados y auto-balanceados.
- Programar inserción y borrado en Árboles Rojinegros.

---

## Ejercicio 1 — Construcción manual de un ABB (nivel introductorio)

Dado el siguiente vector de enteros:  
V = [50, 30, 70, 20, 40, 60, 80]


1. Construya **manualmente** un Árbol Binario de Búsqueda (ABB) insertando los elementos en el orden dado.
2. Dibuje el árbol resultante.
3. Indique cuál es la raíz, las hojas y la altura del árbol.

---

## Ejercicio 2 — Recorridos sobre un ABB

Usando el ABB construido en el ejercicio anterior:

1. Escriba la secuencia de nodos obtenida mediante:
   - Recorrido **inorder**
   - Recorrido **preorder**
   - Recorrido **postorder**
2. Explique brevemente por qué el recorrido inorder de un ABB produce una secuencia ordenada.

---

## Ejercicio 3 — Implementación básica de un árbol binario

Implemente en C++ una estructura de nodo para un árbol binario que almacene enteros.

1. Defina la estructura `Nodo`.
2. Implemente una función recursiva para mostrar el recorrido **inorder**.
3. Pruebe la función con un árbol creado manualmente en el `main`.

---

## Ejercicio 4 — Inserción en un Árbol Binario de Búsqueda

Implemente en C++ una función de **inserción en un ABB**.

1. La función debe mantener la propiedad de ABB.
2. Implemente además los recorridos:
   - inorder
   - preorder
3. Analice la complejidad temporal de la inserción en el mejor y peor caso.

---

## Ejercicio 5 — Búsqueda en un ABB

Sobre el ABB implementado:

1. Implemente una función que determine si un valor dado existe en el árbol.
2. Devuelva un puntero al nodo encontrado o `nullptr` si no existe.
3. Analice la complejidad del algoritmo en función de la altura del árbol.

---

## Ejercicio 6 — Cálculo de propiedades del árbol

Implemente funciones recursivas para calcular:

1. La **altura** del árbol.
2. La **cantidad total de nodos**.
3. La **cantidad de hojas**.

Justifique el orden de complejidad de cada función.

---

## Ejercicio 7 — Eliminación de nodos en un ABB

Implemente la operación de **borrado en un ABB**, considerando los tres casos clásicos:

1. Nodo hoja.
2. Nodo con un solo hijo.
3. Nodo con dos hijos (utilizando el sucesor inorder).

Incluya pruebas que muestren el árbol antes y después del borrado usando recorrido inorder.

---

## Ejercicio 8 — Árboles balanceados: análisis conceptual

1. Explique qué problema presentan los ABB no balanceados.
2. Describa la idea general de un **árbol AVL**.
3. Indique qué tipo de rotaciones existen y en qué situaciones se aplican.
4. Compare conceptualmente AVL vs ABB en términos de complejidad.

(No es necesario programar AVL en este ejercicio).

---

## Ejercicio 9 — Introducción a Árboles Rojinegros

Responda conceptualmente:

1. ¿Qué propiedades definen a un Árbol Rojinegro?
2. ¿Por qué garantizan altura O(log n)?
3. Compare Árboles Rojinegros y AVL según el enfoque presentado en Cormen.

Incluya un ejemplo de inserción donde sea necesaria una rotación y recoloreo.

---

## Ejercicio 10 — Implementación de Árbol Rojinegro (nivel avanzado)

Implemente en C++ un **Árbol Rojinegro** que soporte:

1. Inserción de claves enteras.
2. Borrado de claves enteras.
3. Mantenimiento de todas las propiedades del Árbol Rojinegro.
4. Un recorrido inorder para verificar la estructura del árbol.

Requisitos:
- Utilizar rotaciones izquierda y derecha.
- Implementar los casos de corrección tras inserción y borrado.
- Analizar la complejidad temporal de ambas operaciones.

---
