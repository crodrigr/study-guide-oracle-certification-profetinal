# Create Class Abstract

Al diseñar un modelo algunas veces no se quiere instanciar una entidad directamente. Por ejemplo imagine un Canine con las subclass Wolf,Fox, y Coyote. Queremos que otros desarrolladores creen instancias de las subclases, sin embargo no queremos crear instancias de Canine. En otra palabras todos los objetos de Canine tienen una particularidad en tiempo de ejecución. Observe el siguiente ejemplo

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/4db72ca6-db00-4e14-a147-778e709f8a6f)

Las clases **abstract** tiene métodos abstract, los cuales no tiene definición, la subclases son la que tiene que hacer el **override the method**, con que fin se hace esto?. **Aplicar Poliformismo**

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/0214265e-7068-4947-b95d-64478885035a)


### Ejemplo:

En este ejemplo se observa como al definier un objeto de Canine pero se instancia un objeto de clase Fox, y este en tiempo de ejecución llama al método de **getSound()** de la clase **Fox**

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/c0fc0c9c-0668-4506-a435-6d5a24a59414)

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/1d76b65a-d158-4297-a6dc-9d3592ea44e1)

### Reglas class abstract

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/2a6bfcc3-9df8-4db6-b6d6-4e7eb4976ba6)

### Ejemplo de una clases abstract que no cumplen las reglas:

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/9cae5302-ccd6-4059-a156-253b50552c74)

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/9c93b28c-18f1-4510-ac3d-adbcfd1f3470)

### Declaración de abstract method

Los métodos abstractos siempre se declaran sin cuerpo e incluyen **;** y deben ir dentro una clase **abstract**. Una clase abstract tiene los mismo miembros de las clases no abstract, incluye variables,static,instance métodos, constructores.

### las clases abstract no es requisisto que tenga métodos abstractos

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/9802fe03-7517-4e87-842f-f07492711839)

Caso contrario.

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/aad66fad-70db-41d0-945b-a785b026c09c)}}

### abstract modificador puede ir antes o despued del modificador de acceso

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/94d083fc-8469-4d48-945f-179342e9b15f)

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/a76631bd-d70d-4759-8b54-6111d8757c82)

### Clases hijas que no override métodos abstract

Si una clase hija que no va a override método, debe ser **abstract**, y su desendencia debe hacer el **override**

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/0ee1641f-f026-4946-aa79-8be199ee3ff1)

Otro ejemplo donde hay  una mayor desendencia

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/1d99f942-ecb9-47a8-8576-603cfbc179ce)

### Constructor class abstract

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/ac7db87a-0fec-4b6a-a602-ee4730ec2ed8)

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/7c9fb3d8-63a5-4621-a913-34517809041b)

Este ejemplo si compila e imprime **yummy!**. Este es el orden de ejecución:

1. new Platypus(): Llama al constructor por defecto, el cual, no está definido, y este llama automaticamente a constructor de su padre **Mammal**
2. call chew(): en tiempo de ejecución llama a la implementación **chew()** de la clase **Platypus

### Declaraciones invalidas

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/30fad817-c9a9-492b-b3ec-9366a54beb78)

### abstract and final modifires

El **final** no es permitido en class y métodos abstract

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/f140db52-b057-4fd8-83e6-8f90ee37b31d)

### abstract and private modifiers

Un método no puede ser **private** por que no es visible en las subclases. 

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/f1c4291d-9ff3-4209-b1c4-b48ca163a67e)

Este ejemplo:

No compila por que el modificador de acceso del override no puede reducir la visibilidad el método padre. 

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/6111093e-a0d4-428c-9549-ee4e5cd66b3e)

#### abstrct and static modifiers

No puede ser static, por que los métodos static en herrecia se ocultan, no se overriden, por lo tanto, genera error no se puede implementar.

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/1bc22cfa-b0ca-4d2f-8dad-5a0faaa6d38c)

