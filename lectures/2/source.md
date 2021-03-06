## Indice

 1. Repaso Shaders <!-- .element: class="fragment" data-fragment-index="1"-->
 2. Traslación, rotación, escalación y esquilado --> 2d, no lineal,.. <!-- .element: class="fragment" data-fragment-index="2" -->
 3. Espacio homogeneo <!-- .element: class="fragment" data-fragment-index="3" -->
 4.  Traslación, rotación(Euler), escalación y esquilado --> 3d,lineal,.. <!-- .element: class="fragment" data-fragment-index="4" -->
 5.  Rotaciones con matrix ortogonales <!-- .element: class="fragment" data-fragment-index="5" -->
 6. Rotaciones con cuaternios <!-- .element: class="fragment" data-fragment-index="6" -->
 7. Transformaciones de modelado <!-- .element: class="fragment" data-fragment-index="7" -->



## PIPELINE

<a href ="http://processing.org/tutorials/pshader/">
Shaders
</a>
In Processing
```
uniform mat4 transform;
attribute vec4 vertex;
attribute vec4 color;
varying vec4 vertColor;

void main(){
   gl_Position = transform * vertex;
   vertColor = color;
}
```
```
varying vec4 vertColor;

void main(){
  gl_FragColor = vertColor;
}
```



## Transformaciones Bidimensionales 
<img wigth ="500" height="500" src="lectures/2/fig/image1.JPG">


## Transformaciones Bidimensionales

<font color="yellow"> Tranformaciones del objeto vs transformación del sistema de cordenadas</font>

<img wigth ="400" height="400" src="lectures/2/fig/image2.JPG">


## Transformaciones Bidimensionales

<font color="yellow"> Tranformación activa (base canónica) vs Transformación pasiva (cambio de base)</font>

<img src="lectures/2/fig/image3.JPG">


## Transformaciones Bidimensionales

<p align ="left"><font color="yellow">Traslación</font></p>
<img wigth ="400" height="400" src="lectures/2/fig/image4.JPG" align ="left">
<p align ="right">Vectorialmente tenemos:</p>
</br>
<p align ="right"><p align ="botton"><font color="#00FFFF">
$\begin{bmatrix} 
x \cr 
y \end{bmatrix}
\begin{bmatrix} 
d_x \cr 
d_y \end{bmatrix}
\begin{bmatrix} 
x' \cr 
y' \end{bmatrix}$
</font></p></p>
</br>
<p align ="right"><p align ="botton"><font color="#01DF3A">
$
P'= P + T
$
</font></p></p>


## Transformaciones Bidimensionales

<p align ="left"><font color="yellow">Escalamiento</font></p>
<img wigth ="400" height="400" src="lectures/2/fig/image5.JPG" align ="left">
<p align ="right">Vectorialmente tenemos:</p>
</br>
<p align ="right"><p align ="botton"><font color="#00FFFF">
$\begin{bmatrix} 
x \cr 
y \end{bmatrix}
\begin{bmatrix} 
s_x & 0 \cr 
0 & s_y \end{bmatrix}
\begin{bmatrix} 
x' \cr 
y' \end{bmatrix}$
</font></p></p>
</br>
<p align ="right"><p align ="botton"><font color="#01DF3A">
$
P'= S * P
$
</font></p></p>


## Transformaciones Bidimensionales

<p align ="left"><font color="yellow">Rotación</font></p>
<img wigth ="400" height="400" src="lectures/2/fig/image6.JPG">


## Transformaciones Bidimensionales
<table width="350" heigth="500" border="0" align ="right">
<tr>
<td>
<img src="lectures/2/fig/image7.JPG" width="350" heigth="350">
</td>
</tr>
<tr>
<td>
<font size ="5">Vectorialmente tenemos:</font>
</br>
<font size ="5" color="#00FFFF">
$\begin{bmatrix} 
x \cr 
y \end{bmatrix}
\begin{bmatrix} 
cos\beta & -sen \beta  \cr 
sen \beta & cos \beta \end{bmatrix}
\begin{bmatrix} 
x' \cr 
y' \end{bmatrix}$
</font>
</br>
<font size ="5" color="#01DF3A">
$
P'= R * P
$
</font>
</td>
</tr>
</table> 
<p align ="left"><font color="yellow">Rotación</font></p>
</font></p>
<p align ="left"><font size ="6">De la triangulación obtenemos:</font></p>
<p align ="left"><font size ="6" color="blue">
$x = rcos \alpha$
</font></p>
<p align ="left"><font size ="6" color="blue">
$y= rsen \alpha$
</font></p>
<p align ="left"><font size ="5" color="red">
$x'= rcos (\alpha+\beta) = rcos \alpha cos \beta - rsen \alpha sen \beta $
</font></p>
<p align ="left"><font size ="5" color="red">
$y'= rsen (\alpha+\beta) = rcos \alpha sen \beta - rsen \alpha cos \beta $
</font></p>
<p align ="left"><font size ="6" color="#01DF3A">
$\boxed {x'= xcos \beta - ysen \beta}$
</font></p>
<p align ="left"><font size ="6" color="#01DF3A">
$\boxed {y'= xsen \beta + ycos \beta}$
</font></p>


## Transformaciones Bidimensionales
<p align ="left"><font color="red">Rotación</font></p>
<img wigth ="800" height="250" src="lectures/2/fig/image8.JPG">
<p align ="left">Se tiene </p>
$x' = x + h *y, y'=y$
<p align ="left">,donde h es el parametro del esquilado, esto da:</p>
<font size ="5" color="yellow">
$
D_x=\begin{bmatrix} 
1 & h \cr 
0 & 1 \end{bmatrix}
D_y=\begin{bmatrix} 
1 & 0 \cr 
h & 1 \end{bmatrix}
P'= {D_x \above 1.5pt D_y} * P
$
</font>


## next one




