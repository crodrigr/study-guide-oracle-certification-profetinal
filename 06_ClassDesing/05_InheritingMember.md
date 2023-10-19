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

