# Create Class Abstract

Al diseñar un modelo algunas veces no se quiere instanciar una entidad directamente. Por ejemplo imagine un Canine con las subclass Wolf,Fox, y Coyote. Queremos que otros desarrolladores creen instancias de las subclases, sin embargo no queremos crear instancias de Canine. En otra palabras todos los objetos de Canine tienen una particularidad en tiempo de ejecución. Observe el siguiente ejemplo

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/4db72ca6-db00-4e14-a147-778e709f8a6f)

Las clases **abstract** tiene métodos abstract, los cuales no tiene definición, la subclases son la que tiene que hacer el **override the method**, con que fin se hace esto?. **Aplicar Poliformismo**

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/0214265e-7068-4947-b95d-64478885035a)


#### Ejemplo:

En este ejemplo se observa como al definier un objeto de Canine pero se instancia un objeto de clase Fox, y este en tiempo de ejecución llama al método de **getSound()** de la clase **Fox**

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/c0fc0c9c-0668-4506-a435-6d5a24a59414)

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/1d76b65a-d158-4297-a6dc-9d3592ea44e1)

#### Reglas class abstract

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/2a6bfcc3-9df8-4db6-b6d6-4e7eb4976ba6)

#### Ejemplo de una clases abstract que no cumplen las reglas:

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/9cae5302-ccd6-4059-a156-253b50552c74)

![image](https://github.com/crodrigr/study-guide-oracle-certification-profetinal/assets/31961588/9c93b28c-18f1-4510-ac3d-adbcfd1f3470)

#### Declaración de abstract method

Los métodos abstractos siempre se declaran sin cuerpo e incluyen **;** y deben ir dentro una clase **abstract**. Una clase abstract tiene los mismo miembros de las clases no abstract, incluye variables,static,instance métodos, constructores.


