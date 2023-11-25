# AnimacionesCSS
Repo que contiene ejemplos de animaciones, transiciones y transformaciones con css
# Indice

- [Coordenadas en CSS](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
- [Transiciones](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
    - [Sintaxis](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
    - [Composición de la propiedad](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
    - [Ejemplo en código](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
- [Transformaciones](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
    - [Translate](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
    - [Rotate](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
    - [Scale](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
    - [Skew](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
    - [Combinación de transformaciones](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
    - [Will-change](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
- [Animaciones](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
    - [Animation-name](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
    - [Animation-duration](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
    - [Animation-delay](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
    - [Animation-iteration-count](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
    - [Animation-direction](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
    - [Animation-fill-mode](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
    - [Animation-play-state](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
    - [Animation-timing-function](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
    - [Ejemplo completo](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)
- [Links importantes](https://www.notion.so/Animaciones-en-CSS-1260f10c78fc46f8af5e72535e56d836?pvs=21)

# Coordenadas en CSS

la x funciona como en matematicas, pero y esta ‘alreves’ de lo convencional

![Coordenadas en CSS](https://cs.wellesley.edu/~cs110/reading/L06/images/coordinates.png)

# Transiciones

Las transiciones se refieren a la animación suave entre los diferentes estados de un elemento, como cambios en propiedades como color, tamaño o posición. Estas transiciones permiten que los cambios visuales en la presentación de una página web ocurran de manera gradual y fluida, en lugar de abrupta.

- Las transiciones necesitan un activador para que funcionen.

## Sintaxis

La sintaxis básica para definir transiciones en CSS utiliza la propiedad **`transition`**.

```css
cs
elemento {
  propiedad: valor_inicial;
  transition: propiedad duración tipo_de_función;
}

elemento:hover {
  propiedad: valor_final;
}
```

Donde:

- **`elemento`**: es el selector del elemento al que se aplicará la transición.
- **`propiedad`**: es la propiedad CSS que se animará durante la transición (por ejemplo, **`color`**, **`width`**, **`height`**, etc.).
- **`valor_inicial`** y **`valor_final`**: son los valores iniciales y finales de la propiedad.
- **`duración`**: es la duración de la transición en segundos o milisegundos.
- **`tipo_de_función`**: es la función de temporización que define cómo la transición avanza con el tiempo

## Composicion de la propiedad

transition es la composición de varias propiedades:

1. transition-property: sirve para  indicar la propiedad a la cual se le va a aplicar una transicion. 
    1. Valor defecto: none
    2. otro valor es all: el cual indica que todas las propiedades que se le puedan aplicar la transicion cambiaran su estado.
2. transition-duration: indica cuanto duran las transiciones. Su valor puede ser en seg o ms. Se pueden colocar mas de un valor, lo cual haria que se intercale el valor de la duracion en cada propiedad.
3. transition-timing-function: define la curva de aceleracion entre el estado inicial y el final. sus valores pueden ser
    1. ease[defecto]
    2. ease-in
    3. ease-out
    4. ease-in-out
    5. linear
    6. steps(number, (start | end)): especifica la progresion de la transicion
        - **`numero_de_pasos`**: Especifica la cantidad de pasos en los que se dividirá la animación.
        - **`start`** o **`end`** (opcional): Determina si el valor final de cada paso se alcanza al comienzo (**`start`**) o al final (**`end`**) de cada paso. El valor predeterminado es **`end`**.
    7. curva de bazier: eje x tiempo de la trancision y eje y la progresion. En esa pagina se pueden crear las curvas. 
        
        [cubic-bezier.com](https://cubic-bezier.com/#.17,.67,.83,.67)
        
4. transition-delay: tiempo de espera para que la transicion se ejecute. Si se colocan tiempos negativos, lo que significa que ya paso ciertos segundos de la transicion; es decir si el valor fuera -1 comenzaría la animacion en el segundo 2

## Ejemplo en código

 

```css
/*Elemto a animar*/
.element{
    width: 200px;
    height: 200px;
    background-color: tomato;
    margin: 20px;
    clip-path: circle(80%); /*estado inicial*/
    
		/*Transicion*/
    transition-property: clip-path, transform;
    transition-duration: 2s;
    transition-timing-function: ease-in;
    transition-delay: 0s,3s;

}
/*se recomienda envolver el elemento en un div*/
.container:hover .element{
    clip-path: circle(20%);
    transform: translate(100%);
}
```

Ejemplo en una sola Linea

```css
.element{
    width: 200px;
    height: 200px;
    background-color: tomato;
    margin: 20px;
    clip-path: circle(80%); /*estado inicial*/
    
		/*Transicion*/
    transition: clip-path transform, 2s, ease-in, 0s 33s;
}

.container:hover .element{
    clip-path: circle(20%);
    transform: translate(100%);
}
```

# Transformaciones

Las transformaciones se refieren a un conjunto de funciones que permiten modificar la apariencia y posición de elementos en una página web. Estas transformaciones pueden aplicarse a elementos HTML, como imágenes, textos o cualquier otro contenido visual, y se utilizan para  rotar, escalar, segar y trasladar.
Su mayor ventaja es que no se ejecuten en etapa de  layout. 

## Translate

Mueve un elemento a lo largo de un eje específico. Puede usar cualquier valor de medida.
El porcentaje  es relativo al elemento. 

Se puede utilizar de 3 formas:

- translateX()
- translateY()
- translate():  translate shorthand de x y y. Si se pone solo 1 valor lo toma para x.
Nota: cuando translate tiene un valor diferente de none se crea un concepto de apilamiento

```css
.container{
    width: 90%;
    margin: 30px auto;
    border: 5px solid black;
    display: flex;
    align-items: center;
}
.element{
    background-color: steelblue;
    width: 200px;
    height: 200px;
    margin: 20px;
    transition: transform 1s;
}
.container:hover .element{
    transform: translate(100px, 50px);
    z-index: -1;
}
```

## Rotate

Rota un elemento alrededor de un punto específico. Solo permite valores angulares:

- 0-360 deg
- 0-400 grad
- 0-6.28319 rad
- 0-1 turn

Esta propiedad se puede combinar con transform-origin

Transform-origin: 50% 50%; es el punto de partida, por defecto es 50%.
Se puede usar % o top, bottom, left, right, center

```css
transform: rotate(45deg);
```

## Scale

Cambia el tamaño de un elemento en relación con su tamaño original. acepta numeros enteros, negativos o decimales

- scaleX(-1)
- scaleY(2)
- scale(2.5)

```css
transform: scale(1.5);
```

## Skew

Deforma un elemento en función de los ángulos especificados.

No se recomienda utilizarla porque ya no es compatible en algunos navegadores, lo mejor es usar skewX y skewY.

Solo acepta valores angulares es decir:

- 0-360 deg
- 0-400 grad
- 0-6.28319 rad
- 0-1 turn

```css
transform: skewX(40deg) skewY(60deg);
```

---

Estas transformaciones pueden combinarse y aplicarse de forma secuencial para lograr efectos más complejos. Por ejemplo:

```css
transform: translate(50px, 50px) rotate(45deg) scale(1.5);
```

## will-change

will change nos permite decirles a los navegadores que una propiedad va a cambiar antes de que pase.
Permite optimizar recursos pero lo mejor es no utilizarlo, tan solo que sea el ultimo recurso.
No hay que abusar de las animaciones
Si se va a cambiar la capa de layout si es mejor utilizar will-change
will-change:width,height;
en performance se debe ver si las animaciones funcionan bien
tienen que correr a 60fps

# Animaciones

Una animación es una técnica que permite cambiar gradualmente las propiedades de un elemento a lo largo del tiempo, creando efectos visuales dinámicos. A diferencia de las transiciones no necesita un activador.

> no es recomendable animar muchos estilos
> 

Las animaciones en CSS se definen mediante la regla **`@keyframes`** y la propiedad **`animation`**. Aquí hay un ejemplo básico:

```css
@keyframes mover {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(200px);
  }
}

.elemento {
  animation: mover 2s ease-in-out infinite;
}
```

Los componentes clave de una animación en CSS son:

- **`@keyframes`:** Define los estados intermedios de la animación a lo largo del tiempo.
    - se puede colocar solo el final y se tomara su declaracion como
    estado inicial
    - se pueden colocar tambien porcentajes
    - puede usarse from, to
    - % tambien son validos
- **`animation`:** Aplica la animación a un elemento específico, especificando la duración, la función de temporización, la dirección, entre otros.

> Animation tambien es un shorthand, como atributos obligatorios hay que colocar la referencia y la duracion de la animacion. Los parametros se pueden colocar en cualquier orden.
> 

## animation-name

Es el nombre de la animación definida con **`@keyframes`**

```css
animation-name: grow, giraCody;
```

## animation-duration

Especifica la duración de la animación en segundos o milisegundos.

```css
animation-duration: 1s, 3s;
```

## animation-delay

Tiempo de retardo o espera para que se ejecute una animacion.

```css
animation-delay: 0s, 1s;
```

## animation-iteration-count

Cuantas veces se repite la animacion

```css
animation-iteration-count: 2.5;
```

## animation-direction

define la direccion de la animacion

- por defecto 0-100 normal
- 100-0 reverse
- 0-100-0 alternate
- 100-0-100 alternate-reverse

## animation-fill-mode

define si los estilos cambian o se mantienen al terminar la animacion

- por defecto es none
- forwards es que se queda con el estilo de la animacion
- backwards comienza con los estilos de la animacion en el 0%
- both aplica backwards y forwards

```css
animation-fill-mode: forwards ;
```

## animation-play-state

permite pausar y reaunudar la animacion

- por defecto es running
- paused pausa... lol

```css
animation-play-state: paused;
```

## animation-timing-function

igual a transition timing function

```css
animation-timing-function: cubic-bezier(0.075, 0.82, 0.165, 1);
```

### Ejemplo completo

```css
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
body{
    background-color: rgb(88, 88, 223) ;
    color: white;
    font-family: arial;
    height: 100vh;
    display: flex;
}
.texts{
    margin: auto;
    text-align: center;
}
.title{
    clip-path: polygon(0 0, 0 0, 0 100%, 0 100%);
    animation: show 3s forwards;
    /*
        https://bennettfeely.com/clippy/
    */
    
}
.cody{
    display: block;
    margin: 0 auto;
    width: 200px;
    
    animation-name: grow, giraCody;
    animation-duration: 1s, 3s;
    animation-delay: 0s, 1s;
    animation-iteration-count: 2.5;
    animation-direction: alternate;
    animation-fill-mode: forwards ;
    animation-play-state: paused;
    animation-timing-function: cubic-bezier(0.075, 0.82, 0.165, 1);
}   
.cody:hover{
    animation-play-state: running;
}

@keyframes giraCody{
    /*como inicia equivalente a 0%*/
    from{
        
        opacity: .5;
        filter: grayscale(0.3);
        transform: scale(0.3) translateY(-30%) rotate(30deg);
    }
    /*como termina equivalente a 100%*/

}
@keyframes grow{
    to{
        transform: scale(1.5);
    }
}
@keyframes show{
    to{
        clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%);
    }
}
```

# Links importantes

crear figuras para animarlas con  la propiedad clip-path:

[Clippy — CSS clip-path maker](https://bennettfeely.com/clippy/)

revisar que propiedades son animables:

[Animatable CSS properties - CSS: Cascading Style Sheets](https://udn.realityripple.com/docs/Web/CSS/CSS_animated_properties)
