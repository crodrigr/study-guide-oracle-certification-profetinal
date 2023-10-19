# Initialize class

La inicialización de una clase en Java, especialmente en el contexto de la herencia, implica la creación de objetos y la ejecución de constructores de clases tanto en la superclase como en las subclases. La herencia en Java sigue un proceso específico de inicialización que es importante entender. Aquí hay una descripción general de cómo se inicializan las clases en el contexto de la herencia:

1. **Superclase:** 
   - Cuando se crea un objeto de una subclase, Java primero inicializa la superclase.
   - Se llama al constructor de la superclase. Si no se especifica explícitamente un constructor, se llama al constructor predeterminado (sin argumentos).
   - Los constructores de la superclase se ejecutan en orden desde la clase base hasta la clase más derivada. Esto garantiza que se inicialicen las clases base antes de las clases derivadas.

2. **Subclase:**
   - Después de la inicialización de la superclase, se procede a la inicialización de la subclase.
   - Se llama al constructor de la subclase. Si no se especifica explícitamente un constructor, se llama al constructor predeterminado (sin argumentos).
   - Los constructores de la subclase se ejecutan después de los constructores de la superclase.
   - La subclase puede llamar al constructor de la superclase usando `super()`, lo que permite inicializar variables específicas de la subclase antes de que se complete la inicialización de la subclase.

Ejemplo de inicialización de clases en herencia:

```java
class Superclass {
    int superValue;

    Superclass() {
        superValue = 100;
        System.out.println("Constructor de Superclass");
    }
}

class Subclass extends Superclass {
    int subValue;

    Subclass() {
        super(); // Llama al constructor de la superclase
        subValue = 200;
        System.out.println("Constructor de Subclass");
    }
}

public class Main {
    public static void main(String[] args) {
        Subclass obj = new Subclass();
        System.out.println("superValue: " + obj.superValue);
        System.out.println("subValue: " + obj.subValue);
    }
}
```

En este ejemplo, cuando se crea un objeto de `Subclass`, primero se inicializa la `Superclass` y luego se inicializa la `Subclass`. Los constructores se ejecutan en orden, y el constructor de `Superclass` se llama explícitamente usando `super()` en el constructor de `Subclass`.

La salida sería:

```
Constructor de Superclass
Constructor de Subclass
superValue: 100
subValue: 200
```

Es importante entender este proceso de inicialización de clases en herencia para garantizar que las variables y la lógica de inicialización se manejen correctamente en tus programas Java.

##### Sin super subclase

Si no utilizas la palabra clave `super()` en el constructor de una subclase, Java automáticamente invocará el constructor predeterminado (sin argumentos) de la superclase. Esto es lo que sucede por defecto cuando no proporcionas explícitamente una llamada a `super()` en el constructor de una subclase. Esto es importante para comprender cómo se maneja la inicialización de la superclase en el contexto de la herencia.

Aquí tienes un ejemplo para ilustrar lo que sucede cuando no utilizas `super()` en el constructor de la subclase:

```java
class Superclass {
    int superValue;

    Superclass() {
        superValue = 100;
        System.out.println("Constructor de Superclass");
    }
}

class Subclass extends Superclass {
    int subValue;

    Subclass() {
        // No se utiliza super() aquí
        subValue = 200;
        System.out.println("Constructor de Subclass");
    }
}

public class Main {
    public static void main(String[] args) {
        Subclass obj = new Subclass();
        System.out.println("superValue: " + obj.superValue);
        System.out.println("subValue: " + obj.subValue);
    }
}
```

En este ejemplo, no se utiliza `super()` en el constructor de `Subclass`. Sin embargo, Java invocará automáticamente el constructor predeterminado de `Superclass` antes de inicializar la `Subclass`. La salida será la misma que en el ejemplo anterior:

```
Constructor de Superclass
Constructor de Subclass
superValue: 100
subValue: 200
```

Si la superclase no tiene un constructor predeterminado (sin argumentos), entonces deberás proporcionar una llamada explícita a uno de los constructores de la superclase utilizando `super()` en el constructor de la subclase.
