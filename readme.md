# CSS ESCALABLE

- CSS PLANO : solo una hoja de estilo css, no permite modularizar el codigo, sobreescritura, especificidad, escabilidad (css plano no es recomendable para la escabilidad).
  
   1. Desventajas del CSS Plano
- Mantenimiento Difícil: Las hojas de estilo largas y complejas pueden ser difíciles de mantener y actualizar.
- Repetición de Código: No hay una forma efectiva de reutilizar el código CSS, lo que lleva a la repetición de estilos similares.
- Escalabilidad: Al trabajar en proyectos grandes, manejar múltiples hojas de estilo y reglas CSS puede volverse complejo y propenso a errores.
- Falta de Variables y Funciones: CSS plano no soporta variables, funciones o cualquier otra característica que permita una mayor modularidad y reutilización del código.
  
  1. Ventajas de los Preprocesadores
- Modularidad: Permiten dividir el CSS en varios archivos y modular el código para una mejor organización.
- Variables: Posibilitan el uso de variables para almacenar valores repetidos, como colores y tamaños.
- Anidamiento: Facilitan el anidamiento de selectores, lo que hace que el CSS sea más legible y estructurado.
- Funciones y Mixins: Ofrecen funciones y mixins para reutilizar bloques de código y aplicar estilos de manera más eficiente.
- Mantenibilidad: Hacen que el código CSS sea más fácil de mantener y actualizar.

# PRE PROCESADORES

es un lenguaje que extiende o deriva de css
- STYLUS
- LESS 
- SASS (no es un lenguaje que el navegador va a interpretar, sino que debe tener un **compilador** que va atransformarlo a codigo css, y es lo que va a leer el navegador)
  
todo codigo css es valido con sass, lo reconoce de forma directa, pero no viceversa, es decir, de sass a css. 

  
- FLUJO DE TRABAJO
una carpeta para todos los archivos sass, todos archivos sass tienen que compilar en el ARCHIVO PRINCIPAL DE SASS, y solo se genera un archivo css que se linkea al html. 

1. UN COMPILADOR : archivo principal sass que compila todos los archivos sass generados. 

# VARIABLES 
Las variables en SASS permiten almacenar valores que pueden reutilizarse en todo el documento.

```css
$primary-color: #333;

body {
  color: $primary-color;
}
```

# SCOPE
Las variables tienen un alcance especifico, dentro de un bloque. 

```css
.container {
$padding: 10px;
padding: $padding;
}
```
# ANIDAMIENTO 
SASS permite anidar selectores de la misma manera que HTML está anidado, lo que mejora la legibilidad del código.

```css
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;

    li { 
      display: inline-block; 
    }
  }
}
```

# AMPERSAN - PADRE &
se utiliza para referirse al selector padre dentro de una regla anidada.

```css
a {
  color: blue;

  &:hover {
    color: red;
  }
}
```

# IMPORT 
permite dividir el código SASS en múltiples archivos y luego importarlos en un archivo principal.

``` css
// _reset.scss
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

// styles.scss
@import 'reset';

body {
  font-family: Arial, sans-serif;
}
```