<center>
    <h1>Programación 2</h1>
    <h3>Práctica 6: Programación Orientada a Objetos</h3>
    <h5>1er cuatrimestre 2026</h5>
</center>

## Objetivos de la práctica
* Identificar correctamente relaciones de:
  * “es un” (herencia)
  * “tiene un” (composición)
  * “es parte de un” (agregación)
* Comprender el uso de:
  * métodos virtuales
  * sobreescritura de métodos
  * atributos públicos, protegidos y privados
* Entender la dinámica del despacho dinámico (dynamic dispatch).
* Diseñar interfaces utilizando clases abstractas.
* Implementar soluciones en C++ aplicando buenas prácticas básicas.

# Recomendaciones generales
* Todos los ejercicios deben resolverse en C++17.
* Separar las clases en archivos `.hpp` y `.cpp`.
* Evitar atributos públicos salvo que exista una justificación clara.
* Utilizar `override` cuando se sobrescriban métodos virtuales.
* Reflexionar sobre el diseño antes de programar.

---

# Ejercicio 1 – Detectando relaciones

Para cada uno de los siguientes casos indicar:
* si existe una relación “es un”
* si existe una relación “tiene un”
* si existe una relación “es parte de un”
* justificar la decisión

1. Un auto tiene un motor.
2. Un alumno pertenece a una universidad.
3. Un perro es un animal.
4. Un teclado pertenece a una computadora.
5. Un profesor trabaja en una universidad.
6. Un círculo es una figura geométrica.
7. Un libro tiene capítulos.
8. Una playlist contiene canciones.
9. Un avión tiene turbinas.
10. Un celular utiliza una batería.

### Responder:

* ¿Qué diferencia existe entre composición y agregación?
* ¿Qué objetos pueden existir independientemente?
* ¿Qué relación implica mayor acoplamiento?

---

# Ejercicio 2 – Primera jerarquía de herencia


Implementar las siguientes clases:

* `Animal`
* `Perro`
* `Gato`

La clase `Animal` debe tener:

* atributo protegido `nombre`
* constructor
* método `hacerSonido()`

Las clases derivadas deben redefinir el método.

## Requisitos

* Utilizar herencia pública.
* Mostrar el uso de `override`.
* Instanciar objetos y probar comportamiento.

### Responder:

* ¿Qué significa que `Perro` “es un” `Animal`?
* ¿Por qué conviene reutilizar código mediante herencia?
* ¿Qué problemas aparecerían si se duplicara código?

---

# Ejercicio 3 – Atributos privados, protegidos y públicos

Crear las clases:

* `Persona`
* `Empleado`

### Requisitos

`Persona` debe tener:

* atributo privado `dni`
* atributo protegido `nombre`
* atributo público `edad`

`Empleado` debe heredar de `Persona`.

Intentar acceder desde distintos lugares a cada atributo y documentar:

* qué accesos funcionan
* cuáles producen error
* por qué ocurre

### Responder:

* ¿Por qué normalmente los atributos deberían ser privados?
* ¿Cuándo podría tener sentido utilizar `protected`?
* ¿Qué riesgos tiene dejar atributos públicos?

---

# Ejercicio 4 – Composición

Diseñar las clases:

* `Motor`
* `Auto`

El `Auto` tiene un `Motor`.

### Requisitos

* El motor debe crearse junto con el auto.
* Si el auto se destruye, el motor también.
* El motor debe tener:

  * potencia
  * encendido/apagado

### Responder:

* ¿Por qué esta relación es composición?
* ¿Puede existir el motor fuera del auto en este diseño?
* ¿Qué ocurriría si el motor fuera compartido entre autos?

---

# Ejercicio 5 – Agregación

Implementar:

* `Jugador`
* `Equipo`

El equipo contiene jugadores, pero los jugadores pueden existir independientemente.

### Requisitos

* Crear jugadores fuera del equipo.
* El equipo debe almacenar referencias o punteros.
* Un jugador puede cambiar de equipo.

### Responder:

* ¿Por qué esta relación no es composición?
* ¿Quién “posee” realmente a los jugadores?
* ¿Qué ventajas tiene esta independencia?

---

# Ejercicio 6 – Métodos virtuales

Implementar:

* `Figura`
* `Circulo`
* `Rectangulo`

`Figura` debe declarar:

```cpp
virtual double area() const = 0;
```

Las clases derivadas deben implementar el cálculo.

## Requisitos

* Utilizar punteros a `Figura`.
* Crear un vector heterogéneo.
* Recorrerlo calculando áreas.

* ¿Qué sucede si `area()` NO es virtual?
* ¿Cómo decide el programa qué método ejecutar?
* ¿Qué ventaja aporta el polimorfismo?

---

# Ejercicio 7 – Clase abstracta

Diseñar:

* `Dispositivo`
* `Impresora`
* `Scanner`

`Dispositivo` no debe poder instanciarse.

Debe declarar:

```cpp
virtual void conectar() = 0;
```

## Requisitos

* Implementar comportamientos distintos.
* Verificar que no puede crearse un objeto `Dispositivo`.

### Responder:

* ¿Por qué tiene sentido que `Dispositivo` sea abstracta?
* ¿Qué obliga a implementar una interfaz abstracta?
* ¿Qué ventajas tiene definir contratos?

---

# Ejercicio 8 – Sobreescritura y override

Implementar:

* `Empleado`
* `Gerente`
* `Desarrollador`

Todos deben implementar:

```cpp
virtual double calcularSalario() const;
```

Cada clase derivada debe redefinir el cálculo.

## Requisitos

* Utilizar `override`.
* Mostrar comportamiento polimórfico.

### Responder:

* ¿Qué errores ayuda a detectar `override`?
* ¿Qué diferencia existe entre sobrecarga y sobreescritura?

---

# Ejercicio 9 – Constructores y destructores en herencia

Implementar:

* `Vehiculo`
* `Auto`
* `Camion`

Agregar mensajes en:

* constructores
* destructores

## Requisitos

* Mostrar el orden de ejecución.
* Agregar destructor virtual en la clase base.

### Responder:

* ¿Qué problema puede ocurrir si el destructor NO es virtual?
* ¿Qué orden siguen constructores y destructores?

---

# Ejercicio 10 – Sistema de notificaciones

Diseñar un sistema con:

* `INotificador`
* `EmailNotificador`
* `SMSNotificador`
* `PushNotificador`

La interfaz debe definir:

```cpp
virtual void enviar(const std::string& mensaje) = 0;
```

## Requisitos

* Utilizar un vector de punteros a interfaz.
* Enviar mensajes a todos los notificadores.

### Responder:

* ¿Por qué conviene programar contra interfaces?
* ¿Qué ocurre si mañana aparece `TelegramNotificador`?
* ¿Qué principio de diseño aparece acá?

---

Implementar:

* `Personaje`
* `Guerrero`
* `Mago`
* `Arquero`

Todos deben tener:

* vida
* ataque()
* defender()

Cada tipo ataca diferente.

## Requisitos

* Utilizar métodos virtuales.
* Simular un combate simple.

### Responder:

* ¿Qué ventajas tiene representar personajes mediante una clase base?
* ¿Cómo se extendería el sistema?

---

# Ejercicio 12 – Biblioteca digital

Implementar:

* `Material`
* `Libro`
* `Revista`
* `Biblioteca`

La biblioteca contiene materiales.

## Requisitos

* Usar polimorfismo para mostrar información.
* La biblioteca debe almacenar distintos tipos de materiales.

### Responder:

* ¿Por qué conviene almacenar punteros a `Material`?
* ¿Qué pasaría si la biblioteca guardara objetos por valor?

---

# Ejercicio 13 – Sistema de sensores

### Diseñar:

* `Sensor`
* `SensorTemperatura`
* `SensorPresion`
* `EstacionMeteorologica`

La estación tiene sensores.

## Requisitos

* Cada sensor debe implementar:

```cpp
virtual double medir() = 0;
```

* La estación debe consultar todos los sensores.

### Responder:

* ¿Por qué los sensores deberían compartir interfaz?
* ¿Qué ventaja tiene desacoplar la estación de sensores concretos?

---

# Ejercicio 14 – Detectando errores de diseño

Analizar las siguientes afirmaciones y explicar si el diseño es correcto o incorrecto:

1. “Un motor hereda de auto.”
2. “Una universidad hereda de profesor.”
3. “Una clase base tiene atributos públicos para simplificar.”
4. “No hace falta usar métodos virtuales.”
5. “Las interfaces son innecesarias en programas chicos.”

### Responder:

* ¿Qué consecuencias tienen estos errores?
* ¿Cómo afectan el mantenimiento?
* ¿Cómo afectan la reutilización?

---

# Ejercicio 15

Desarrollar un sistema de gestión de transporte.

## Requisitos mínimos

### Jerarquía principal

Implementar:

* `Vehiculo`
* `Auto`
* `Moto`
* `Camion`

### Relaciones

* Un vehículo tiene un motor.
* Una empresa de transporte posee vehículos.
* Los choferes pueden manejar distintos vehículos.

### Polimorfismo

Implementar:

```cpp
virtual double costoOperativo() const = 0;
```

### Interfaces

Definir:

```cpp
class IMantenible
```

con:

```cpp
virtual void realizarMantenimiento() = 0;
```


### Responder:

* ¿Qué decisiones de diseño tomaron?
* ¿Qué partes podrían extenderse fácilmente?
* ¿Dónde aparece desacoplamiento?
* ¿Qué ocurriría si no existieran interfaces?

---
# Ejercicio 16 - Preguntas

1. ¿Cuándo conviene usar herencia?
2. ¿Cuándo conviene usar composición?
3. ¿Qué significa “programar contra interfaces”?
4. ¿Qué problema resuelve el polimorfismo?
5. ¿Qué diferencia existe entre relación estructural y reutilización?
6. ¿Qué ventajas aporta el encapsulamiento?
7. ¿Por qué las clases abstractas ayudan al diseño?
8. ¿Qué diferencia existe entre acoplamiento fuerte y débil?
