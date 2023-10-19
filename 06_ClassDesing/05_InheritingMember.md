# Inheriting Members

En la herencia la clases hijas puede hacer un override de los métodos que tiene la misma signature (nombre metodo, parametros y tipos) y el tipo de dato
quere retorna, no incluye los operadores de acceso, especificaciones especiales, o cualquier exception. 

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/b891ec9e-87ae-4a33-b41a-835572e227e8)

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/e2e219fa-3d02-445e-9489-791a1e14e28d)

En este ejemplo se aplica el overriden sin problema, getAverageWith() llama a super reference. 

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/cc50097b-f2f7-4c40-92f8-c7a122dd09e8)

Se debe usar el super, por que si no se crea un loop

### Reglas

- 1. Los metodos de las clases hijas debe tener la misma signature del metodos del padre.
- 2. El método de la clase hija debe ser del mismo nivel de acceso de mayor accesibilidad.
- 3. El método de la clase hija no debe declara a checked exception nueva o mas amplia de la exception del métod padre.
- 4. Si el método retorna dato, debe ser del mismo del padre o subtipo. Se conoce como Covariant return types.

**Regla 3 expection**

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/e42c94bb-43f1-4dcc-abef-5717273ebdd8)

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/6d3739bc-cdd7-4f21-bdc7-a3f0be4a3c40)

**Regla 4 convariant return types**

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/3b9aba0a-2925-4950-82e3-4ac207f8b68e)

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/258a5233-4a56-4f27-96ab-a47f42bd9ee6)

### Redeclaring private methods

Los métodos que son private no se puede hacer override en las clases hijas, por que no tienen aceso a eso métodos de los padres por el modificador
de acceso. **Java permite crear un métod con la misma signature que del padre, pero no lo trata como un override del metodo del padre, sino como un método nuevo e independiente

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/ce274ddd-5546-4642-8b7a-d138cf713b20)


### Hiding Static Methods

En Java, el ocultamiento de métodos estáticos (hiding static methods) es un concepto relacionado con la herencia y las clases. Se refiere a la capacidad de una subclase (clase hija) para definir un método estático con el mismo nombre que un método estático en su clase base (clase padre), pero sin considerarse una anulación (override) en el sentido tradicional de la herencia. 

Diferencias clave entre el ocultamiento de métodos estáticos y la anulación de métodos:

1. **Anulación (Override):** En la anulación, las subclases redefinen métodos no estáticos de la clase base con la misma firma (nombre y parámetros) y el mismo tipo de retorno. Esto permite que las subclases proporcionen implementaciones específicas de esos métodos.

2. **Ocultamiento (Hiding):** En el ocultamiento de métodos estáticos, las subclases pueden definir métodos estáticos con el mismo nombre que los métodos estáticos de la clase base, pero esto no es considerado una anulación. En lugar de anular el método de la clase base, se proporciona una nueva implementación en la subclase, y la implementación de la clase base no está disponible a través de una referencia de la subclase.

Veamos un ejemplo para entenderlo mejor:

```java
class Parent {
    static void staticMethod() {
        System.out.println("Método estático de Parent");
    }
}

class Child extends Parent {
    static void staticMethod() {
        System.out.println("Método estático de Child");
    }
}

public class Main {
    public static void main(String[] args) {
        // El ocultamiento se aplica a los métodos estáticos
        Parent.staticMethod();  // Llama al método estático de Parent
        Child.staticMethod();   // Llama al método estático de Child
    }
}

```

**Ejemplo valido**

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/3ad94bd1-3e55-44f8-b6bc-eecdd8b68308)

**Ejemplo error**

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/d402cb2a-a6a7-4a07-91c2-993b7ad62d37)


### Hiding variable

El "hidden variable" (variable oculta) en Java se refiere al comportamiento en el que una variable con el mismo nombre en una superclase y en una subclase puede ocultar (shadow) la variable en la superclase en el ámbito de la subclase. Esto puede llevar a situaciones donde el código en la subclase se refiere a la variable local de la subclase en lugar de la variable en la superclase con el mismo nombre. Este comportamiento puede ser sorprendente y potencialmente propenso a errores si no se maneja adecuadamente.

Veamos un ejemplo de variable oculta en Java:

```java
class Parent {
    int x = 10;
}

class Child extends Parent {
    int x = 20;
    
    void printX() {
        System.out.println(x); // Se refiere a la variable local de Child, no a la de Parent
    }
}
```

En este ejemplo, la clase `Child` tiene una variable llamada `x` que oculta la variable `x` de la clase `Parent`. La llamada a `printX` en la clase `Child` imprimirá `20`, ya que se refiere a la variable local de `Child`, y no a la variable de `Parent`.

Para evitar situaciones de ocultamiento de variables, es una buena práctica utilizar la notación `super` para acceder a la variable de la superclase cuando sea necesario. Por ejemplo:

```java
class Child extends Parent {
    int x = 20;
    
    void printX() {
        System.out.println(super.x); // Accede a la variable de Parent
    }
}
```

De esta manera, se puede acceder explícitamente a la variable de la superclase cuando sea necesario y evitar confusiones en el código.

En resumen, el ocultamiento de variables se refiere al comportamiento en el que una variable en una subclase con el mismo nombre que una variable en la superclase oculta la variable en la superclase en el ámbito de la subclase. El uso de la palabra clave `super` es útil para acceder a la variable de la superclase en tales casos.

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/ab0aecc5-17c6-4a7f-b459-31f4ef6d7426)

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/88ddb105-f59d-497e-87e8-b584d281566e)

### Writing final method

En Java, puedes declarar un método como `final` en una clase para evitar que las subclases lo anulen. Un método `final` es un método que no puede ser modificado o anulado en una subclase. Esto puede ser útil cuando deseas asegurarte de que un método en una superclase mantenga su implementación original en todas las subclases. Aquí tienes un ejemplo de cómo declarar un método `final` en una clase de superclase y luego intentar anularlo en una subclase:

```java
class Superclass {
    public final void finalMethod() {
        System.out.println("Este es un método final en la superclase.");
    }
}

class Subclass extends Superclass {
    // Esto generará un error de compilación, ya que no puedes anular un método final.
    // @Override
    public void finalMethod() {
        System.out.println("Intento de anular un método final en la subclase.");
    }
}

public class Main {
    public static void main(String[] args) {
        Superclass superClass = new Superclass();
        superClass.finalMethod();  // Llama al método final de la superclase.

        Subclass subClass = new Subclass();
        subClass.finalMethod();  // Esto causará un error de compilación.
    }
}
```

En este ejemplo, `finalMethod` en la clase `Superclass` se declara como `final`, lo que significa que no se puede anular en subclases. Cuando intentas anularlo en la clase `Subclass`, obtendrás un error de compilación.

Usar métodos `final` en herencia es una técnica útil para proteger ciertas funcionalidades de la superclase y garantizar que no se modifiquen en las subclases. Sin embargo, debes usar esta característica con moderación, ya que la capacidad de anular métodos es una de las ventajas fundamentales de la herencia en Java.

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/33ccad8e-d3a0-4b58-bb6e-d9a227e79bd9)

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/3aed2faf-bd3e-4595-9fab-3e5aae273e2f)

