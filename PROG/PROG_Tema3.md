# **UD3: Utilización de Objetos**

## **1. Introducción a los objetos y la Programación Orientada a Objetos**

### ¿Qué es un objeto?
Un objeto representa una **entidad del mundo real** con características propias y comportamientos definidos. Por ejemplo:

- **Coche:**
  - **Características (atributos):** marca, color, velocidad.
  - **Comportamientos (métodos):** acelerar, frenar, girar.

Los objetos en un programa tienen tres elementos clave:
- **Estado:** Definido por los atributos del objeto.
- **Comportamiento:** Acciones que puede realizar (métodos).
- **Identidad:** Un identificador único que diferencia un objeto de otros.

### ¿Qué es la Programación Orientada a Objetos (POO)?
La **POO** es un paradigma que organiza los programas en términos de objetos, acercando la lógica de los programas al mundo real. Esto mejora la **legibilidad** y facilita las **modificaciones** en el software.

### Ventajas de la POO
- Representación más **natural** del problema del mundo real.
- **Mayor legibilidad** del código.
- Facilita el **mantenimiento y modificación** del software.
- Mejora la **reutilización** del código.

---

## **2. Fundamentos de la POO**

### **Conceptos básicos**

1. **Clase:** 
   - Es el molde o plantilla que define las características (atributos) y comportamientos (métodos) comunes a un grupo de objetos.
   - Ejemplo: La clase `Coche` puede tener atributos como `marca` y `color`, y métodos como `acelerar` y `frenar`.

2. **Objeto:**
   - Es una **instancia de una clase**. Cada objeto tiene un estado único basado en los valores de sus atributos.
   - Ejemplo: Un objeto de la clase `Coche` puede ser un Toyota rojo que va a 60 km/h.

3. **Atributos:**
   - Variables que almacenan los datos o propiedades de un objeto.
   - Ejemplo: `color = "rojo"`, `marca = "Toyota"`.

4. **Métodos:**
   - Funciones definidas dentro de una clase que describen los comportamientos de sus objetos.
   - Ejemplo: `acelerar()` aumenta la velocidad del coche.

5. **Encapsulación:**
   - Los datos de un objeto están protegidos y solo son accesibles a través de los métodos definidos.

6. **Herencia:**
   - Permite que una clase hija herede atributos y métodos de una clase padre.

7. **Polimorfismo:**
   - Los métodos pueden comportarse de manera diferente según el objeto que los invoque.

---

### **Diferencias entre POO y Programación Estructurada**

| **POO**                                | **Programación Estructurada**            |
|----------------------------------------|------------------------------------------|
| Los programas se organizan en objetos. | Los programas se organizan en funciones. |
| Datos y métodos se agrupan en objetos. | Los datos y funciones están separados.   |
| Facilita el mantenimiento y la seguridad. | Más propenso a errores al modificar datos globales. |
| Mejora la reutilización del código.    | Difícil reutilizar código.               |

---

## **3. Beneficios de la POO**

1. **Comprensión:**
   - Refleja los conceptos del problema del mundo real, facilitando la lectura y comprensión del código.

2. **Modularidad:**
   - El código se organiza en módulos independientes (clases), mejorando la organización.

3. **Fácil mantenimiento:**
   - Las modificaciones son más sencillas, ya que los datos y las acciones están estrechamente relacionados.

4. **Seguridad:**
   - Los datos no pueden modificarse directamente; solo a través de los métodos definidos.

5. **Reusabilidad:**
   - Los objetos y clases pueden reutilizarse en diferentes programas o partes del código.

---

## **4. Caso práctico: gráfico de barras tridimensional**

### Problema
Crear un gráfico de barras tridimensional que:
- Contenga **dos series de datos**.
- Eje horizontal: números del 1 al 11.
- Eje vertical: valores de 0 a 1000 con una escala de 200.

### Solución usando POO en Java

#### Clase principal
```java
public class Grafico3D {
    public static void main(String[] args) {
        // Crear las dos series de datos
        Serie serie1 = new Serie("Ventas", new int[]{200, 400, 600, 800, 1000, 900, 700, 500, 300, 400, 600});
        Serie serie2 = new Serie("Beneficios", new int[]{100, 200, 300, 400, 500, 450, 350, 250, 150, 200, 300});

        // Crear el gráfico
        GraficoBarras3D grafico = new GraficoBarras3D();
        grafico.addSerie(serie1);
        grafico.addSerie(serie2);

        // Dibujar el gráfico
        grafico.dibujar();
    }
}

## 2.3.- Características

Cuando hablamos de Programación Orientada a Objetos, existen una serie de características que se deben cumplir. Cualquier lenguaje de programación orientado a objetos las debe contemplar. Las características más importantes del paradigma de la programación orientada a objetos son:

### Abstracción

Es el proceso por el cual definimos las características más importantes de un objeto, sin preocuparnos de cómo se escribirán en el código del programa, simplemente lo definimos de forma general. En la Programación Orientada a Objetos, la herramienta más importante para soportar la abstracción es la clase. Básicamente, una clase es un tipo de dato que agrupa las características comunes de un conjunto de objetos.

Poder ver los objetos del mundo real que deseamos trasladar a nuestros programas, en términos abstractos, resulta de gran utilidad para un buen diseño del software, ya que nos ayuda a comprender mejor el problema y a tener una visión global de todo el conjunto. Por ejemplo, si pensamos en una clase `Vehículo` que agrupa las características comunes de todos ellos, a partir de dicha clase podríamos crear objetos como `Coche` y `Camión`. Entonces se dice que `Vehículo` es una abstracción de `Coche` y de `Camión`.

### Modularidad

Una vez que hemos representado el escenario del problema en nuestra aplicación, tenemos como resultado un conjunto de objetos software a utilizar. Este conjunto de objetos se crean a partir de una o varias clases. Cada clase se encuentra en un archivo diferente, por lo que la modularidad nos permite modificar las características de la clase que define un objeto, sin que esto afecte al resto de clases de la aplicación.

### Encapsulación

También llamada "ocultamiento de la información". La encapsulación o encapsulamiento es el mecanismo básico para ocultar la información de las partes internas de un objeto a los demás objetos de la aplicación. Con la encapsulación, un objeto puede ocultar la información que contiene al mundo exterior, o bien restringir el acceso a la misma para evitar ser manipulado de forma inadecuada.

Por ejemplo, pensemos en un programa con dos objetos, un objeto `Persona` y otro `Coche`. `Persona` se comunica con el objeto `Coche` para llegar a su destino, utilizando para ello las acciones que `Coche` tenga definidas como por ejemplo `conducir`. Es decir, `Persona` utiliza `Coche` pero no sabe cómo funciona internamente, sólo sabe utilizar sus métodos o acciones. Dentro de un objeto están sus datos, a los que se accede a través de sus funciones o métodos.

### Jerarquía

Mediante esta propiedad podemos definir relaciones de jerarquías entre clases y objetos. Las dos jerarquías más importantes son la jerarquía "es un" llamada generalización o especialización y la jerarquía "es parte de", llamada agregación. Conviene detallar algunos aspectos:

- **Generalización o especialización (Herencia)**: Permite crear una clase nueva en términos de una clase ya existente (herencia simple) o de varias clases ya existentes (herencia múltiple). Por ejemplo, podemos crear la clase `CocheDeCarreras` a partir de la clase `Coche`, y así sólo tendremos que definir las nuevas características que tenga.
  
- **Agregación (Inclusión)**: Permite agrupar objetos relacionados entre sí dentro de una clase. Así, un `Coche` está formado por `Motor`, `Ruedas`, `Frenos` y `Ventanas`. Se dice que `Coche` es una agregación y `Motor`, `Ruedas`, `Frenos` y `Ventanas` son agregados de `Coche`.

### Polimorfismo

Esta propiedad indica la capacidad de que varias clases creadas a partir de una antecesora realicen una misma acción de forma diferente. Por ejemplo, pensemos en la clase `Animal` y la acción de expresarse. Nos encontramos que cada tipo de `Animal` puede hacerlo de manera distinta, los Perros ladran, los Gatos maullan, las Personas hablamos, etc.

Dicho de otra manera, el polimorfismo indica la posibilidad de tomar un objeto (de tipo `Animal`, por ejemplo), e indicarle que realice la acción de expresarse, esta acción será diferente según el tipo de mamífero del que se trate.

Los conceptos de herencia y polimorfismo serán trabajados en profundidad en las próximas unidades.

## 2.4.- Lenguajes de programación orientados a objetos

Una panorámica de la evolución de los lenguajes de programación orientados a objetos hasta llegar a los utilizados actualmente es la siguiente:

- **Simula (1962)**: El primer lenguaje con objetos fue `B1000` en 1961, seguido por `Sketchpad` en 1962, el cual contenía clones o copias de objetos. Sin embargo, fue `Simula` el primer lenguaje que introdujo el concepto de clase, como elemento que incorpora datos y las operaciones sobre esos datos. En 1967 surgió `Simula 67` que incorporaba un mayor número de tipos de datos, además del apoyo a objetos.

- **SmallTalk (1972)**: Basado en `Simula 67`, la primera versión fue `Smalltalk 72`, a la que siguió `Smalltalk 76`, versión totalmente orientada a objetos. Se caracteriza por soportar las principales propiedades de la Programación Orientada a Objetos y por poseer un entorno que facilita el rápido desarrollo de aplicaciones. El Modelo-Vista-Controlador (MVC) fue una importante contribución de este lenguaje al mundo de la programación. El lenguaje `Smalltalk` ha influido sobre otros muchos lenguajes como `C++` y `Java`.

- **C++ (1985)**: `C++` fue diseñado por Bjarne Stoustrup en los laboratorios donde trabajaba, entre 1982 y 1985. Lenguaje que deriva del `C`, al que añade una serie de mecanismos que le convierten en un lenguaje orientado a objetos. No tiene recolector de basura automática, lo que obliga a utilizar un destructor de objetos no utilizados. En este lenguaje es donde aparece el concepto de clase tal y como lo conocemos actualmente, como un conjunto de datos y funciones que los manipulan.

- **Eiffel (1986)**: Creado en 1985 por Bertrand Meyer, recibe su nombre en honor a la famosa torre de París. Tiene una sintaxis similar a `C`. Soporta todas las propiedades fundamentales de los objetos, utilizado sobre todo en ambientes universitarios y de investigación. Entre sus características destaca la posibilidad de traducción de código `Eiffel` a Lenguaje `C`. Aunque es un lenguaje bastante potente, no logró la aceptación de `C++` y `Java`.

- **Java (1995)**: Diseñado por Gosling de Sun Microsystems a finales de 1995. Es un lenguaje orientado a objetos diseñado desde cero, que recibe muchas influencias de `C++`. Como sabemos, se caracteriza porque produce un bytecode que posteriormente es interpretado por la máquina virtual. La revolución de Internet ha influido mucho en el auge de `Java`.

- **C# (2000)**: El lenguaje `C#`, también conocido como Sharp, fue creado por Microsoft como una ampliación de `C` con orientación a objetos. Está basado en `C++` y en `Java`. Una de sus principales ventajas es que evita muchos de los problemas de diseño de `C++`.

En la actualidad muchos lenguajes de programación, incluso algunos que originalmente no fueron concebidos para ser orientados a objetos como `Javascript` o `PHP`, están migrando a la orientación a objetos.

### Autoevaluación

Relaciona los lenguajes de programación indicados con la característica correspondiente, escribiendo el número asociado a la característica en el hueco correspondiente.

| Lenguaje de programación | Relación | Tiene la característica de que … |
|--------------------------|----------|----------------------------------|
| Java                     | 3        | Produce un bytecode para ser interpretado por la máquina virtual. |
| SmallTalk                | 2        | Introdujo el concepto del Modelo-Vista-Controlador. |
| Simula                   | 1        | Fue el primer lenguaje que introdujo el concepto de clase. |
| C++                      | 4        | Introduce el concepto de clase tal cual lo conocemos, con atributos y métodos. |

---

## 3.- Clases y Objetos. Características de los objetos

### Caso práctico

María ha hecho un descanso de cinco minutos. Se está tomando un café y está repasando los conceptos de Programación Orientada a Objetos. Piensa que este paradigma supone un cambio de enfoque con respecto a las técnicas tradicionales. Ahora lo que necesita es ahondar en el concepto de objeto, que parece ser el eje central de este modelo de programación.

Al principio de la unidad veíamos que el mundo real está compuesto de objetos, y podemos considerar objetos casi cualquier cosa que podemos ver y sentir. Cuando escribimos un programa en un lenguaje orientado a objetos, debemos identificar cada una de las partes del problema con objetos presentes en el mundo real, para luego trasladarlos al modelo computacional que estamos creando.

En este contexto, un objeto de software es una representación de un objeto del mundo real, compuesto de una serie de características y un comportamiento específico. Pero ¿qué es más concretamente un objeto en Programación Orientada a Objetos? Veámoslo.

Un objeto es un conjunto de datos con las operaciones definidas para ellos. Los objetos tienen un **estado** y un **comportamiento**.

### Características de los objetos

Los objetos tienen unas características fundamentales que los distinguen:

- **Identidad**: Es la característica que permite diferenciar un

# Utilización de objetos en Programación Orientada a Objetos

## Caso práctico

María sigue fuera de la oficina. Esta noche en casa quiere repasar conceptos sobre Programación Orientada a Objetos, así que aprovecha un momento para llamar a Juan y le comenta:

- **María**: Ya sé todo sobre objetos, solo me falta saber... ¿cómo se crea un objeto?

- **Juan**: (sonríe) Los objetos se crean de manera similar a declarar una variable, pero en vez de utilizar un tipo de dato primitivo, usas una clase. Luego, instancias el objeto con la palabra clave `new` para reservar memoria y, a partir de ahí, puedes acceder a sus atributos y métodos usando el operador punto.

- **María**: ¡Ah, gracias! Esta noche le echo un vistazo.

### Creación de un Objeto

Cuando creamos una clase, podemos generar objetos a partir de ella en nuestro programa. Los objetos son instancias de las clases, es decir, un objeto es una realización concreta de una clase. A efectos prácticos, los términos "objeto" e "instancia" se utilizan de manera similar, aunque "instancia" hace referencia a un objeto específico de una clase particular.

### Ejemplo de Objeto y Clase

**Analogía**: Imagina que tienes un molde para galletas. El molde define las características de la galleta (su forma y tamaño), y las galletas creadas a partir de este molde son los objetos.

Si tenemos una clase `Persona` con atributos como `colorDePelo`, `peso`, `altura`, y métodos como `crecer()`, `dormir()`, `comer()`, entonces podemos crear un objeto llamado `Trabajador` que es una instancia de la clase `Persona`. El objeto `Trabajador` tiene sus propios valores para esos atributos, pero sigue el mismo formato y comportamientos definidos por la clase `Persona`.

Los objetos contienen copias de los atributos definidos en la clase. Así, cada objeto ocupa un espacio en memoria donde se almacenan sus datos, y esos datos pueden ser manipulados por sus métodos.

---

### Autoevaluación

Las variables instancia son un tipo de variables miembro.

- **Verdadero**
- **Falso**

---

## 4.1.- Ciclo de vida de los objetos

El ciclo de vida de un objeto en programación se puede dividir en tres fases:

1. **Creación**: Se reserva memoria e inicializan los atributos del objeto.
2. **Manipulación**: Se usan los atributos y métodos del objeto.
3. **Destrucción**: El objeto es eliminado y los recursos que ocupaba son liberados.

### Recolección de basura

Cuando un objeto ya no se usa, Java lo elimina automáticamente usando el recolector de basura, lo cual libera memoria que puede ser utilizada por otros objetos.

---

## 4.2.- Declaración de objetos

Para crear un objeto, se deben seguir dos pasos:

### 1. Declaración

Definir el tipo de objeto, que corresponde a la clase de la que se creará el objeto:

```java
<tipo> nombre_objeto;
