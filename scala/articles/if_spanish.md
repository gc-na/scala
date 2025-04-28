<!--
Meta Description: # La Declaración "if" en Scala: Guía Completa y Práctica ## Sinopsis La declaración `if` en Scala es una estructura de control fundamental que permite...
Meta Keywords: scala, else, código, que, declaración
-->

# La Declaración "if" en Scala: Guía Completa y Práctica

## Sinopsis
La declaración `if` en Scala es una estructura de control fundamental que permite ejecutar código condicionalmente, facilitando la toma de decisiones en el flujo de ejecución de un programa.

## Documentación
La declaración `if` en Scala se utiliza para evaluar una expresión booleana y, dependiendo de su resultado (verdadero o falso), ejecutar un bloque de código específico. Esta característica es esencial para implementar lógica condicional en aplicaciones Scala.

### Uso
La sintaxis básica de la declaración `if` es la siguiente:

```scala
if (condición) {
  // bloque de código si la condición es verdadera
} else {
  // bloque de código si la condición es falsa (opcional)
}
```

Además, Scala permite usar `if` como una expresión, lo que significa que puede devolver un valor. Esto es útil para asignar resultados basados en condiciones.

### Detalles
- **Condicional Simple**: Evalúa una única condición.
  
  ```scala
  val resultado = if (x > 10) "Mayor que 10" else "10 o menos"
  ```

- **Condicional Anidado**: Permite tener múltiples condiciones utilizando `else if`.

  ```scala
  val resultado = if (x > 10) "Mayor que 10" 
                  else if (x < 10) "Menor que 10" 
                  else "Igual a 10"
  ```

- **Sin `else`**: Es posible omitir la cláusula `else`, en cuyo caso, si la condición es falsa, el resultado será `Unit` (equivalente a `void` en otros lenguajes).

## Ejemplos
1. **Ejemplo Básico**:

   ```scala
   val numero = 5
   if (numero > 0) {
     println("El número es positivo.")
   }
   ```

2. **Ejemplo con `else`**:

   ```scala
   val numero = -3
   if (numero > 0) {
     println("El número es positivo.")
   } else {
     println("El número es negativo o cero.")
   }
   ```

3. **Ejemplo con `else if`**:

   ```scala
   val numero = 0
   if (numero > 0) {
     println("El número es positivo.")
   } else if (numero < 0) {
     println("El número es negativo.")
   } else {
     println("El número es cero.")
   }
   ```

4. **Uso como expresión**:

   ```scala
   val x = 15
   val mensaje = if (x > 10) "Mayor que 10" else "10 o menos"
   println(mensaje)
   ```

## Explicación
Al usar la declaración `if`, es importante tener en cuenta lo siguiente:

- **Tipado**: Si `if` se utiliza como expresión, todos los bloques de código dentro de las condiciones deben devolver el mismo tipo de valor.
- **Bloques de Código**: Cada bloque de código debe estar correctamente delimitado por llaves `{}` si contiene más de una línea de código.
- **Ejecución de Código**: Solo se ejecuta el bloque correspondiente a la primera condición verdadera. Las demás condiciones se ignoran.
- **Puntos de Confusión**: En Scala, la ausencia de un bloque `else` puede resultar en un error si se espera que la declaración `if` devuelva un valor.

## Resumen en Una Línea
La declaración `if` en Scala es una estructura de control que permite ejecutar bloques de código basados en la evaluación de condiciones booleanas.