# Politopos

## Resumen: Quiral polyhedra from a PC construction

Dado un 4-politopo regular $\mathcal{T}$, la construcción central del artículo es:

1. Calcular el poliedro de Petrie-Coxeter $PC_\alpha(\mathcal{T})$. Resulta ser regular o de clase $2_{\{0,2\}}$.
2. Aplicar la halving operation para obtener $PC_\alpha(\mathcal{T})^\eta$.
3. Aplicar la operación de 2-facetting (2-hole) para obtener $(PC_\alpha(\mathcal{T})^\eta)^\phi:=H_\alpha(\mathcal{T})$. Éste es un poliedro regular o quiral.

Se hizo este procedimiento para cada uno de los 4-politopos regulares (6 convexos y 10 estrellados). Veamos cómo analizar los poliedros resultantes:

De la regularidad de $\mathcal{T}$ podemos estudiar la simetría de $H_\alpha(\mathcal{T})$. Mientras que $G(\mathcal{T})=\langle R_0,R_1,R_2,R_3\rangle$ como en la construcción Wythoff, resulta que $G(H_\alpha(\mathcal{T}))= \langle S_1,S_2\rangle$, donde
$$
S_1=R_0R_1R_3R_2\\
S_2=R_2R_1
$$
Aquí, $S_1$ es un tornillo y $S_2$ una rotación, dando lugar a la notación $\{\frac{p}{p_1,p_2},q\}$ donde $q$ es el orden de la rotación y los enteros $p,p_1$ y $p_2$ caracterizan al tornillo. Esto sugiere qué clase de poliedro es $H_\alpha(\mathcal{T})$: tiene caras helicoidales, $q$ en cada vértice.

 En este punto toda la información sobre $H_\alpha(\mathcal{T})$ debe estar al alcance de unas cuentas. Podemos darle coordenadas y encontrar una expresión en forma de orden parcial. (observación: hay un teorema en el artículo que nos dice que cualquier poliedro quiral con caras helicoidales debe ser combinatoriamente regular).

## Primer intento de plantear el problema

**¿Alguno de estos poliedros es la celda de un 4-politopo?**

Caso conocido: combinatoriamente, $H_\alpha(\{3,3,3\})$ es un dodecaedro, o sea que en este caso la respuesta debe ser que sí--- este poliedro es cualquier celda de la 120-celda $\{5,3,3\}$.

## Ayuda del equipo

### Ideas random

> Topologically, combinatorial equivalence corresponds to the existence of a (piecewise linear) homeomorphism between the polytopes P ∼= Q that restricts to homeomorphisms between the facets (and hence all the faces)
>
> of P and Q. In other words, P ∼= Q if and only if P and Q define isomorphic cell complexes (CW-balls) — see Munkres [418] or Björner [89, Sect. 12] [96, Sect. 4.7] for these concepts.
>
> <P align="right">
> Ziegler, Lectures on Polytopes
> </P>

### Comentarios de Briseida

Tenemos las rotaciones $S_1$ y $S_2$ que generan el grupo de simetrías de $H_\alpha(\{5,3,3\})$. Basta confirmar que existe una tercera transformación $S_3$ tal que mediante la construcción de Wythoff se obtenga un 4-politopo. Debemos centrar nuestra atención en una transformación que intercambie aristas. ¿Cómo funciona la construcción de Wythoff para 4-politopos? **¿Qué simetría deberíamos agregar a $H_\alpha(\{3,3,3\})$ para generar un 4-politopo regular?**

### Charla de Bris

**Teorema.** Sea $G=\langle S_1, S_2\rangle$ un grupo discreto, donde $S_1$ y $S_2$ son isometrías de $\mathbb{R}^n$ con $(S_1S_2)^2=1$ y además

* $\langle S_1\rangle\cap\langle S_2\rangle=1$
* Si $p$ es del orden de $S_1$ y $q$ es del orden de $S_2$, con $p,q>2$

Condiciones geométricas

* $\text{Stab}(v)=\langle S_2\rangle$
* $\text{Stab}(e)=\langle S_1, S_2\rangle$
* $\text{Stab}(f)=\langle S_1\rangle$

Lo demás

* $v\in\text{fix}S_2$ y $v\notin\text{fix}S_1$
* $e=\{v,vS_1^{-1}\}$
* $f=\{v,e\}\langle S_1\rangle$
* $v\langle S_1,S_2\rangle=V$
* $eG=E$
* $fG=F$

Ese conjunto $P(S_1,S_2)$ es un politopo geométrico.

Veamos esta construcción: tomamos un 4-politopo esférico regular $\mathcal{T}=\{p,q,r\}$

$\phi R_i=\phi^i$ son las banderas base (adyacentes). ¿$S_1$ como producto de las $R_i$? Si definimos $S_1=R_0R_1R_2R_3$, resulta que esto es un Petrie, es una hélice. Ahora sí ¿qué neceisto para definir $S_2$ y que sí quede un poliedro.

Tomemos el grupo $[p,q,r]^+$, el grupo de rotaciones del politopo. Quitamos las simetrías de orden:

* 2
* Polígonos de Petrie de la fig. $\{q,r\}$ que no cumplan
* $(S_1S_2)^2=1$

Toma el ejemplo de la 120-celda. Hace un dibujo de la figura vértice ve, enumera los vértices y define las $R_i$ en términos de esos nombres como permutaciones. Queda que no queda.

Para el cubo de roli, de nuevo $S_1=R_0R_1R_2R_3$ y ahora $S_2=R_3R_2R_1R_3$ no jala pero $S'_2=R_3R_2R_1R_2$ sí.

Para la 24 celda, como $|\text{Stab}_Gg|=8$ y $|\langle S_2\rangle|=4$, no se puede.

Para la 600-celda, $S_2=R_3R_2R_1R_2$, $S_2'=R_3R_2R_1R_3$, $S_2''=(R_1R_3R_2)^2$. $|\text{Stab}v|=60$, $\langle S_2\rangle$.

### Charla de Gasde

#### Parte I

* Full rank: dimensión del espacio es igual al rango del politopo (para politopos finitos). Dimensión del espacio es uno menos que el rango del politopo infinito (por ejemplo teselaciones).

* Quasi-regular polytope. Es hereditario (las simetrías de cada cara son simetrías del politopo) y sus facetas son regulares.

   * O bien tiene una órbita en caras y es regular
   * O bien tiene dos tipos de facetas y dos órbitas en banderas.
   * Son transitivos en vértices.

* *Extra* Uniforme:= (la definición cambia) caras regulares y transitivo en vértices

* Un poliedro cuasi-regular tiene grupo de simetrías $G(\mathcal{P})=\langle R,S,T\rangle$ con $R^2=S^2=T^2=(RS)^s=(RT)^t=(ST)^r$.

   * $R$ es la que va por el punto medio de la arista y esto es cierto para las dos caras diferentes
   * $S$ y $T$ son las que pasan por el vértice y el centro de cada cara.
   * Observemos que no hay la de la arista, pues si la hubiera sólo habría un tipo de cara

* Operaciones

   * Facetado. Si $r=2$ es decir $ST$ es un medio giro. Ahora $ST$ va a jugar el papel de $R_1$ es decir fija al vértice y pasa por el centro de la cara. Al componer $(ST)R$ obtenemos la rotación en el centro de la cara
      $$
      (R,S,T)\xrightarrow{\varphi}(R,ST=TS,T)\\
      (R,S,T)\xrightarrow{\varphi}(R,S,ST=TS)
      $$
      Por ejemplo, el cuboctaedro se convierte en una cosa con caras cuadradas (o triangulares, dependiendo de qué facetado hagamos) y hexagonales, pues $(ST)R$ es de orden 6.

      o si $r=3$
      $$
      (R,S,T)\xrightarrow{\varphi}(R,STS=TST,T)\\
      (R,S,T)\xrightarrow{\varphi}(R,S,TST=STS)
      $$
      Por ejemplo, el facetado del cuboctaedro (creo que) es:
      
      <img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230412112316505.png" alt="image-20230412112316505" style="zoom:50%;" />
      
   * Centrinvertion=centrinversión. Sólo para poliedros finitos que tienen un centro u origen. Aquí cambiamos una de las simetrías generadoras, que son involuciones, por la involución respecto al complemento ortogonal del plano o recta que definen la inovlución original. Es decir, si es un plano lo mando al semigiro respecto a la recta ortogonal al plano que pasa por $O$ y al revés. Soñé que me rapaba la mitad de la cabeza, con rasuradora, ¡Ay!

      Bueno esto es:
      $$
      \varphi:(R,S,T)\xrightarrow{\zeta}(R^\perp,S,T)
      $$

      * Esto parece generar caras alabeadas (skew).

      > Observaciones de Isa:
      >
      > * $v$ el vértice original no puede quedar fijo por $R^\perp$ porque si así fuera entonces sería $O$ el punto fijo de todo.
      > * Si la inversión central está en $G(P)=\langle R,S,T\rangle$ entonces $R^\perp\in G(P)$, pues $RR^\perp=$ inversión central.
      
      * Si la inversión central ya está en el grupo, esta operación no hace nada. Si no está, el grupo cambia.

* Hay 25 poliedros cuasiregulares con caras planas regulares. (Asia, Egon)

* Puedes aplicar el faceteado a politopos regulares que se pueden bicolorear bien. Por ejemplo octaedro a una cosita, y de hecho ese no se puede centrinvertir porque quedan demasiados skews.

#### Parte II

* Según Así y Egon, va a haber un poliedro regular subyacente, cuyo grupo es irreducible en el espacio. Los vértices del cuasirregular pueden estar en los vértices del regular o en los puntos medios. O sea que puede estar hecho del regular o del medial. Ellos clasificaron todos los cuasirregulares usando estas ideas:
* Hay de dos sopas en esta comida:
   * Caras planas y centrales (el centro de la cara es el centro del poliedro, como el cuboctaedro faceteado)
   * Caras planas no centrales.
      * Aquí, $R$ debe ser una reflexión (si fuera un medio giro, fijaría la arista pero movería al resto del poliedro). Vector de no sé qué (2,2)
      * $(2,2)\xrightarrow{\zeta}(1,2)$
   * Caras alabeadas
      * $R$ es un medio giro. Vector (1,2)
      * $(1,2)\xrightarrow{\zeta}(2,2)$

**Observaciones**

* Caras planas no centrales y alabeadas no son compatibles, es decir no se pueden pegar. O sea tenemos que hacer planas y centrales con alabeadas o planas y no centrales con alabeadas.

* El facetado de caras planas no centrales produce centrales, y el facetado de caras alabeadas produce alabeadas y siguen siendo centrales. ¿Qué pasa con la centrinversión? Bueno las planas no centrales pasa que su vector se convierte en (1,2), y puede ser plana central o alabeada. Luego si tengo una alabeada me da una pareja de dos caras planas no centrales.

En conclusión, podemos convertir uno con caras alabeadas en otro con caras planas mediante la centrinversión:

**Lema** $\mathcal{P}$ sólo tiene caras planas.

**Teorema.** Sea $\mathcal{P}$ un poliedro cuasi-regular (no regular) finito con caras no centrales y el grado de cada vértice es par. Entonces, $\mathcal{P}$ es el medial de un sólido platónico, el medial de un poliedro de Kepler-Poinsot o  pequeño ditrigonal icosadodecaedro o gran ditrigonal icosadodecaedro, o ditrigonal dodecadodecaedro.

Los tres raros tienen los mismos vértices que el dodecaedro.

Primero mostramos los mediales de los sólidos platónicos y de los Kepler-Poinsot, son dos y dos.

<center><img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230412115958510.png" alt="image-20230412115958510" style="zoom:50%;" /><img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230412120009682.png" alt="image-20230412120009682" style="zoom:35%;" /></center>

<img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230412120052745.png" alt="image-20230412120052745" style="zoom:30%;" /><img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230412120116032.png" alt="image-20230412120116032" style="zoom:30%;" />

Ahora los tres raros: (¡ups!)

**Teorema** Sea $\mathcal{P}$ un poliedro cuasi-regular finito con algunas caras centrales. Entonces $\mathcal{P}$ es el medial del Petrie de algún sólido platónico o de alguno de los Kepler-Poinsot.

<img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230412121346456.png" alt="image-20230412121346456" style="zoom:30%;" />

> Éste es el medial del Petrie del tetraedro. Si piensas que el octaedro es cuasi-regular (coloreando alternadamente las caras), puedes facetearlo y obtienes este. Éste no lo puedo centrinvertir porque quedan en cada arista tres polígonos. Es el caso raro de la familia al final de esta historia.

<img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230412121616867.png" alt="image-20230412121616867" style="zoom:30%;" /><img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230412121732566.png" alt="image-20230412121732566" style="zoom:30%;" />

<img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230412121944314.png" alt="image-20230412121944314" style="zoom:25%;" /><img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230412121959891.png" alt="image-20230412121959891" style="zoom:30%;" /><img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230412122040460.png" alt="image-20230412122040460" style="zoom:25%;" /><img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230412122052952.png" alt="image-20230412122052952" style="zoom:25%;" /><img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230412122107975.png" alt="image-20230412122107975" style="zoom:25%;" /><img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230412122122994.png" alt="image-20230412122122994" style="zoom:25%;" />

<img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230412122135675.png" alt="image-20230412122135675" style="zoom:25%;" />

En orden: el medial del Pertie del cubo, octaedro, dodecaedro, icosaedro y los Kepler-Poinsot.

Y ahora hay que rascales la panzita. Quedan cinco familias con seis poliedros cada una y una última familia con un sólo poliedro. Cada familia se obtiene de un poliedro base, maceteando y centrinvirtiendo. Específicamente: facetear con $S$, facetear con $T$, centrinvertir lo que sale, facetear lo que sale. El faceteado de lo centrinvertido es lo mismo sin importar qué camino tomé y además es lo mismo que centrinvertir el original.

Las cinco familias se obtienen empezando con el cuboctaedro, icosidodecaedro, gran icosidodecaedro, dodecadodecaedro, ditrigonal. Ahí hay 15 poliedros. La familia rara es el medial del Petrie del tetredro.

**En total hay 31 poliedros cuasirregulares finitos**: 

* Mediales de los 9 Petries
* Los cinco del cuboctaedro
* Los cinco del icosidodecaedro
* Los cinco del gran icosidodecaedro
* Los cinco del dodecadodecaedro
* Mediales de los 4 Kepler-Poinsot (son dos)

### Comentarios de Isabel sobre el valor de $\alpha$

Distintos valores de $\alpha$ en la construcción de Petrie-Coxeter dan lugar a distintos polihedros. Hay ciertos valores para los cuales las simetrías que generan $H_\alpha(\mathcal{T})$ son simetrías de $\mathcal{T}$. Cuando $\alpha=0$, los vértices de $PC_\alpha(\mathcal{P})$ son los vértices de $\mathcal{P}$.

Cuando $\alpha=0,1$, es posible que algunos de los vértices en la construcción "colapsen". Eso quiere decir que algunos vértices terminan siendo el mismo, y el resultado puede no ser un poliedro. Si, en cambio, aparece el valor 1, leemos que "la cantidad de vértices que colapsan es 1" (para $\alpha=0$ si el 1 está a la izquierda, y respectivamente $\alpha=1$ derecha). Es decir, no hay colapso.

Conviene entonces estudiar los casos donde no hay colapso para $\alpha=0$ pues en este caso la construcción de Petrie-Coxeter nos devuelve una estructura cuyos vértices son los mismos vértices del 4-politopo. Así, podremos usar las simetrías del 4-politopo original.

**Pregunta** En estos casos, Petrie-Coxeter nos deja igual y la operación halving deja de tener sentido (a menos que el 1-esqueleto del 4-politopo inicial tenga caras cuadradas), y pasamos a la operación 2-hole. **¿El cubo de Roli se obtiene al aplicar halving y 2-hole al 1-esqueleto del {4,3,3}? Es decir, ¿se trata del $H_0(\{4,3,3\})$?**

### Análisis del $H_\alpha\{5,3,3\}$

* El tornillo (rotación respecto a la cara) es de orden 30.
* La rotación respecto al vértice es de orden 3.

<center><img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230220113608224.png" alt="image-20230220113608224" style="zoom:30%;" /><img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230220113652701.png" alt="image-20230220113652701" style="zoom:25%;" /></center>

Las matrices que corresponden a estas transformaciones en $\mathbb{R}^4$ son:
$$
\begin{align*}
S_1=\frac{1}{2}\begin{pmatrix}
\varphi & 1 & 0 & \varphi^{-1}\\
1 & -1 & -1 & 1\\
0 & 1 & \varphi^{-1} & \varphi\\
\varphi^{-1} & -1 &\varphi&0
\end{pmatrix}
\qquad \qquad 
S_2=\frac{1}{2}\begin{pmatrix}
2&0&0&0\\
0&\varphi&-1&\varphi^{-1}\\
0&-1&-\varphi^{-1}&\varphi\\
0&-\varphi^{-1}&-\varphi&-1
\end{pmatrix}
\end{align*}
$$
Queremos responder: **¿cómo encuentro una $S_3$ que genere un 4-politopo?**

Veamos cómo se encontraron $S_1$ y $S_2$ .......

## Por analogía: A finite quiral 4-polytope in $\mathbb{R}^4$

### Cubos y 4-cubos

Consideremos el 4-cubo, $\{4,3,3\}$.

* Hay una coloración canónica dada por las "direcciones".
* Salvo por una elección, hay otra coloración que también satisface que:
  * En cada vértice inciden 4 colores
  * ~~Cada camino de aristas de dos colores alternantes es un 4-ciclo, ie. un cuadrado combinatorio~~
  * Quitando todas las aristas de algún color, nos queda un cubo combinatorio.

<img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230210102628021.png" alt="image-20230210102628021" style="zoom:20%;" />

Notemos que cuando quitamos todas las aristas verdes del 4-cubo obtenemos dos cubos, el chiquito adentro y el "cubo volteado" que es el exterior del sólido que vemos. ¿Qué pasa si quitamos las aristas verdes de la segunda coloración? Obtenemos el cubo de Roli.

<img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230210105902535.png" alt="image-20230210105902535" style="zoom:20%;" />

##### Breve descripción del cubo de Roli

*Los ciclos de dos colores tienen longitud 8, no 4. Así, es como si las dos caras opuestas de un cubo normal estuvieran de alguna forma fusionadas. Al quitar las aristas verdes del cubo original obtuvimos dos cubos, así que incluso después de fusionar las caras opuestas en estos cubos, tendríamos dos caras. Y sí, de hecho dados dos colores, digamos morado y azul, hay dos ciclos disconexos (y entrelazados como enlace de Hopf) que corresponden a caras "opuestas" del cubo de Roli (Ver imagen, otros colores!).*

<center><img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230219200011049.png" alt="image-20230219200011049" style="zoom:40%;" /><img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230219200107331.png" alt="image-20230219200107331" style="zoom:40%;" /><img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230219200145226.png" alt="image-20230219200145226" style="zoom:40%;" /></center>

*Finalmente las aristas rojas unen estas dos caras opuestas. Como observación adicional, las figuras de Mathematica fueron creadas agregando "tela" entre las aristas y los ejes de rotación, que en este caso son tornillos.*



**Tratando de proceder por analogía, veamos cómo construir el 4-cubo a partir del compuesto de dos cubitos normales o a partir del cubo de Roli.**

Nos fijamos en la figura de vértice: tenemos un triángulo, es una figura del vértice plana. En el centro de ese triángulo hay una rotación de orden 3 que permuta cíclicamente las aristas. Queremos convertir este triángulo en un "solidito", que será un tetraedro: la figura del vértice de un 4-cubo. Sabiendo que la rotación de la arista que buscamos es de orden 3, para definirla basta tomar como eje de rotación cualquier recta que une el vértice negro con alguno de los vértices:

<img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230208140526040.png" alt="image-20230208140526040" style="zoom:25%;" />

Diríamos: $S_3$ es esta rotación, y terminamos.

En el cubo de Roli pasa lo mismo: tomamos una rotación de orden 3 cuyo eje sea cualquiera de las tres aristas incidentes en el vértice y deberíamos reconstruir el 4-cubo original. *Observación* Esta operación distorsiona la coloración.

### Dodecaedros y 4-dodecaedro

Consideremos directamente la figura de vértice de un dodecaedro normal, que también es un triángulo, y sabiendo que que el 4-dodecaedro es el $\{5,3,3\}$, realmente es lo mismo que para el cubo: basta con rotar 120º alrededor de una arista.

La figura de vértice del Half-2-Hole del {5,3,3} para $\alpha=0$ también es un triángulo (ya que la rotación del vértice es de orden 3), y si se nos antoja reconstruir un 4-dodecaedro, conviene intentar rotar 120º alrededor de alguna arista.

Para encontrar esta rotación nos fijamos en las simetrías generadoras del {5,3,3}. Como estamos en $\alpha=0$, podemos tomar la rotación de 120º respecto a la arista base del {5,3,3}. ¿Qué obtenemos al agregar esta rotación?

##### Preguntas

1. En el artículo dice que el $H_0\{5,3,3\}$ se puede tomar como faceta de un 4-politopo *quiral*.

   Debe ser análogo a la coloración del 4-cubo con cubos de Roli. Quiere decir que el 4-dodecaedro cuyas caras son el $H_0\{5,3,3\}$ es un 4-politopo quiral.

2. ¿Cómo voy a saber si al agregar la $S_3$ las cosas pegan bien?

3. ¿Es posible dar una coloración del  $H_0\{5,3,3\}$ análoga al cubo de Roli?

4. Leer el artículo y pensar en el politopo desde $\mathbb{P}^3$.

### Construcciones proyectivas

#### Hemicubo y 4-hemicubo

Identificando puntos antípodas en una esfera que circunscriba un cubo, obtenemos el hemicubo. Se puede ver como una teselación del plano proyectivo y como una gráfica tetraédrica coloreada:

<center><p float="left"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/8d/Hemicube.svg/1280px-Hemicube.svg.png" alt="Hemicube.svg" style="zoom:20%;" />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://upload.wikimedia.org/wikipedia/commons/a/a9/Tetrahedron_3_petrie_polygons.png" alt="Tetrahedron 3 petrie polygons.png" style="zoom:35%;" /></p></center>

Lo análogo se hace para el 4-cubo, y se obtiene la gráfica bipartita $K_{4,4}$, que tiene al menos tres: una "regular" en las direcciones (imágenes de arriba), y dos coloraciones quirales (imágenes de abajo):

<center><img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230220115015677.png" alt="image-20230220115015677" style="zoom:55%;" /><img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230219192806457.png" alt="image-20230219192806457" style="zoom:60%;" /><img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230220111710633.png" alt="image-20230220111710633" style="zoom:55%;" /><img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230220111739855.png" alt="image-20230220111739855" style="zoom:55%;" /></center>

Según el artículo, "las simetrías de este poliedro (el hemihypercube, $\{4,3,3\}/2$" son los automorfismos que preservan la coloración de esta gráfica + las isometrías de $\mathbb{P}^3$ que preservan la gráfica".



#### Hemidodecaedro y 4-hemidodecaedro

Consideremos un dodecaedro normal e identifiquemos puntos antípodas en la esfera. Obetenemos el hemidodecaedro:

<center><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/29/Petersen-graph.png/1280px-Petersen-graph.png" alt="undefined" style="zoom:20%;"/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4d/Petersen_double_cover.svg/1920px-Petersen_double_cover.svg.png" alt="img" style="zoom:15%;" /></center>

Se trata de la gráfica de Petersen. Podemos hacer lo mismo para el 4-dodecaedro. **¿Qué gráfica obtenemos?** Procediendo por analogía respecto al artículo del cubo de Roli, *queremos dar una coloración no canónica de esta gráfica*, lo que nos devolvería un "colorful polytope": sus caras son ciclos de dos colores y sus facetas son las subgráficas quitando un color. De ahí sale que las caras serían hélices (polígonos de Petrie).

Sería cierto entonces que este colorful polytope sería combinatoriamente isomorfo que el 4-hemidodecaedro, pero geométricamente quiral (**Teorema**). En un siguiente paso, se tomaría la doble cubierta de este 4-politopo en $\mathbb{S}^3$ y obtenendríamos el esqueleto del 4-dodedacedro. Tomando en cuenta los colores, tendríamos el famoso $H_0\{5,3,3\}$.

##### Objetivos

1. Descubrir qué gráfica corresponde al 4-hemidodecaedro y **encontrar una coloración especial**.
2. Demostrar que esta coloración es combinatoriamente isomorfa al hemi-120-celda, pero geométricamente quiral.

## Por continuación de Quiral polyhedra ...

Realmente no es necesario construir el $H_0\{5,3,3\}$ por analogía del artículo *A finite quiral...*, de hecho ya tenemos la existencia el poliedro en cuestión. Lo que corresponde ahora es ver cómo relacionar la construcción ya tenemos del Half-2-hole-{5,3,3} y tratar de relacionarla con la construcción del *A finite quiral...*. Sí, debemos tratar de encontrar una coloración del hemi-120-celda o del 120-celda mismo a partir del H2H {5,3,3}.

## Análisis de los H2H de tres 4-politopos estrellados

### Presentación de los 4-politopos

*Hence there are no regular star-polytopes in five or more dimensions. **Regular polytopes, p. 278***

Ya está hecho el trabajo hecho para $H_0\{5,3,3\}$. Para este trabajo nos concentraremos en $H_1\{5,3,5/2\}$, $H_0\{5,3,5/2\}$ y $H_1\{3,3,5/2\}$. Se trata de los quiralitos obtenidos a partir de los 4-politopos estrellados "Gran 120-celda" y "Gran 600-celda", resp. Dos de ellos están escogidos para valores de $\alpha=1$, de forma que en estos dos casos estaremos trabajando con los 4-politopos duales, el {5/2,5,3} "Pequeño 120-celda estelado" y el {5/2,3,3}, "Gran gran 120-celda estelada"

La gran 120-celda tiene dodecaedros como celdas, pero la rotación de la arista es inusual y de hecho la **figura de vértice es un gran icosaedro**, {3,5/2}. En cada vértice inciden cinco triángulos acomodados en pentagrama:

<center><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/eb/Great_icosahedron.png/1280px-Great_icosahedron.png" alt="Great icosahedron.png" style="zoom:25%;" /><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/Great_icosahedron_vertfig.svg/1920px-Great_icosahedron_vertfig.svg.png" alt="Great icosahedron vertfig.svg" style="zoom:15%;" /></center>

Para el pequeño 120-celda su figura de vértice es un dodecaedro, pero **las celdas son pequeños dodecaedros estelados**, {5/2,5}. Son doce pentagramas, cinco en cada vértice:

<center><img src="https://upload.wikimedia.org/wikipedia/commons/7/77/Small_stellated_dodecahedron.png" alt="Small stellated dodecahedron.png" style="zoom:30%;" /><img src="https://upload.wikimedia.org/wikipedia/commons/9/93/Small_stellated_dodecahedron_vertfig.png" alt="Small stellated dodecahedron vertfig.png" style="zoom:40%;" /></center>

Y por último, para la gran gran 120-celda, {5/2,3,3} estelada **las celdas son grandes dodecaedros estelados**, {5/2,3} son doce pentagramas, tres inciden en cada vértice.

<center><img src="https://upload.wikimedia.org/wikipedia/commons/7/77/Great_stellated_dodecahedron.png" alt="Great stellated dodecahedron.png" style="zoom:30%;" /><img src="https://upload.wikimedia.org/wikipedia/commons/6/61/Great_stellated_dodecahedron_vertfig.png" alt="Great stellated dodecahedron vertfig.png" style="zoom:60%;" /></center>

### Cálculo de sus grupos

Bueno, el trabajo por ahora es obtener los grupos de estos tres 4-politopos. Comencemos con el {5,3,5/2}, la gran 120-celda. El grupo se denota [5,3,5/2].

Comencemos con el {5/2,3,3}, la gran gran 120-celda estrellada.

Partiendo de que el grupo de la 120-celda, [5,3,3], está generado por $R_0,R_1,R_2$ y $R_3$ como Wythoff, queremos expresar el grupo en términos de cuatro generadores $T_0,T_1,T_2$ y $T_4$. 

Después de muchos intentos tomamos una bandera básica del medio dodecaedro y del medio gran dodecaedro estrellado:

![New Drawing](/Users/daniel/My Drive (dangcasanova@gmail.com)/Tesis/New Drawing.jpg)



Sucede así:

* $T_0=R_2$
* $T_2=R_0$ en sentido horario con centro en el centro del hemidodecaedro.
* $T_1$ es rotar $R_2$ en sentido antihorario con centro en el centro de la cara base, es decir, $T_1=(R_0R_1)^2R_2(R_0R_1)^{-2}$.

Ahora para encontrar la reflexión $T_3$ recordemos que la composición $T_2T_3$ es la rotación en la arista de orden 3. Aunque esta intuición es correcta, no es claro cómo encontrar $T_3$ en términos de las $R_i$ con esta información.

En los notebooks, resulta que el grupo $[5/2,3,3]=[3,3,5/2]:=\langle T_i\rangle$ está dado en términos del grupo $[5,3,5/2]:=\langle P_i\rangle$ de acuerdo a:

* $T_0=P_3$
* $T_1=(P_2P_1P_0)P_1(P_2P_1P_0)^{-1}$
* $T_2=P_0$
* $T_3=(P_1P_0)P_1(P_1P_0)^{-1}$

¿Qué podemos hacer? Decir cómo están dadas las $P_i$ en términos de las $R_i$ y habríamos terminado.

Bueno, de hecho,

* $P_0=R_0$

* $P_1=(R_1R_2)R_3(R_1R_2)^{-1}$
* $P_2=R_3R_2R_3$
* $P_3=R_2$

Así que a la mera hora:

* $T_0=R_2$
* $T_1=\big((R_3R_2R_3)((R_1R_2)R_3(R_1R_2)^{-1})\big)(R_0)(R_1R_2)R_3(R_1R_2)^{-1}\big(R_3R_2R_3)((R_1R_2)R_3(R_1R_2)^{-1})\big)^{-1}$
* $T_2=R_0$
* $T_3=\big((R_1R_2)R_3(R_1R_2)^{-1})(R_0)\big)((R_1R_2)R_3(R_1R_2)^{-1})\big((R_1R_2)R_3(R_1R_2)^{-1})(R_0)\big)^{-1}$

#### Banderas básicas del {5,3,3} y el {5,3,5/2}

Se logró hacer una gráfica de las proyecciones estereográficas de las banderas básicas del {5,3,3} (azul) y el {5,3,5/2} (verde):

<img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230321175849183.png" alt="image-20230321175849183" style="zoom:50%;" />

Parece (aunque no del todo) que comparten dos caras.

Los únicos que más o menos se parecen son (V4,V1,V2) con (W2,W3,W4). Se debe poder deducir cuál $R_i$ corresponde con (W2,W3,W4) y cuál $T_i$ corresponde con (V4,V1,V2). También hay que arreglar el código.

Se nos antoja construir (a) un dibujo 3D análogo para el {5/2,3,3} y (b) las banderas básicas en el hemidodecaedro para el {5,3,5/2} como en la sección anterior.



#### Después del 24 de marzo

##### Un intento de dibujar las banderas en Mathematica

* De alguna forma dedujeron que el vértice no cambia

Todo comienza con la bandera básica del {3,3,5}. Es un tetraedro que no hemos logrado encontrar en Mathematica. ¿Por qué? Bueno, necesitamos primero el vértice, esto es fácil: $v_0=(1,0,0,0)$. Luego, podemos encontrar la arista haciendo $R_0R_1v_0$, es decir rotando el vértice alrededor de la cara. El punto medio del segmento debería ser parte de la bandera. Luego, deberíamos poder encontrar el centro de la cara intersectando los planos de $R_0$ y $R_1$ con el plano de la cara, que resulta ser el plano de $R_3$. Ahora para encontrar el centro de la celda…

O más bien… abusando de notación y pensando que $R_i$ es el plano de reflexión se nos antoja que…

* $v_0=R_1\cap R_2\cap R_3$
* $v_1=R_0\cap R_2\cap R_3$
* $v_2=R_0\cap R_1\cap R_3$
* $v_3=R_0\cap R_1\cap R_3$

Pero hay algo raro, porque en realidad son hiperplanos, y la intersección de tres hiperplanos es una línea, no un punto. **¿Cómo podemos encontrar la bandera básica?** **Concluimos que nuestro método para encontrar la bandera básica no es el mismo que se usó en los otros notebooks**.

Un comentario extra sobre los valores propios de las reflexiones:

> Schulte, Symmetry of Polytopes and Polyhedra, from Handbook of Discrete and Computational Geometry
>
> Reflection group: A group generated by (hyperplane) reflections in a finite- dimensional space V . In the present context the space is a real or complex vector space (or affine space). A reflection is a linear (or affine) transformation whose eigenvalues, save one, are all equal to 1, while the remaining eigenvalue is a primitive kth root of unity for some k ≥ 2; in the real case the eigenvalue is −1. If the space is equipped with further structure, the reflections are assumed to preserve it. For example, if V is real Euclidean, the reflections are Euclidean reflections.

Se logró: construir la bandera básica del {3,3,5} tomando un vértice, el punto medio de la arista, el centro la cara y el centro de la celda.

Se intentó: hacer lo mismo para el {5,3,5/2}. Falta encontrar el centroide del dodecaedro. Hace falta hacer más ligero el código.

**¿Cómo encontrar este centroide usando las intersecciones de los hiperplanos? Falta: graficar las proyecciones de los hiperplanos.**



##### La cuenta de aquel día: checar que las $P_i$ sean buenas

Recordando que si $[3,3,5]=\langle R_i\rangle$ y $[5,3,5/2]=\langle P_i\rangle$, entonces

* $P_0=R_0$

* $P_1=(R_1R_2)R_3(R_1R_2)^{-1}$
* $P_2=R_3R_2R_3$
* $P_3=R_2$

Queremos asegurarnos de que… 
$$
R_i^2=(R_0R_1)^3=(R_1R_2)^3=(R_2R_3)^5=1\\
(R_0R_2)^2=(R_0R_3)^2=(R_1R_3)^2=1\\ \\

P_i^2=(P_0P_1)^5=(P_1P_2)^3=(P_2P_3)^5=1\\
(P_0P_2)^2=(P_0P_3)^2=(P_1P_3)^2=1
$$
La cuenta del pizarrón fue que:
$$
\begin{align*}
(P_0P_1)^2=\quad& R_0R_1R_2R_3R_2R_1R_0R_1R_2R_3R_2R_1\qquad \textit{quitemos las R...}\\ \\
&01232\mathit{101}2321\\
&01232\mathit{010}2321,\qquad\text{101=010}\\
&01\mathit{0}2321232\mathit{0}1,\qquad\text{conmutamos los 0's}\\
&\mathit{101}232123201,\qquad\text{101=010}\\
&\quad12321232\quad,\qquad\text{¡conjugado de 01!}\\
&\quad123\mathit{121}32\quad,\qquad212=121\\
&\quad12\mathit{1}323\mathit{1}2\quad,\qquad\text{conmutamos los 1's}\\
&\quad\mathit{212}32312\quad,\qquad212=121\\
&\quad\quad2323\quad\quad,\qquad\text{¡conjugado de 21!}
\end{align*}
$$
¡Así que $(P_0P_1)^2$ tiene el mismo orden que $R_2R_3R_2R_3$, 5!

Para $P_2P_3$ tenemos
$$
P_2P_3=R_3R_2R_3R_2=(R_3R_2)^2
$$
O sea que también $(P_2P_3)^5=1$.

Bueno, y por aquí **faltó comprobar que** $(P_1P_2)^3=1$.

##### Los dibujos del otro día: encontrar la bandera básica del {5,3,5/2}

Consideramos un tetraedro (celda) básico del {3,3,5}, que sea el simplejo dado por los vértices 1,2,3 y 4 como a continuación:



ya que es la rotación en el vértice.

<img src="/Users/daniel/Library/Application Support/typora-user-images/image-20230417165521962.png" alt="image-20230417165521962" style="zoom:33%;" />

Entonces: (en los productos voy de derecha a izquierda)

| {3,3,5}                 | {5,3,5/2}                                                    |
| ----------------------- | ------------------------------------------------------------ |
| $R_0=(12)(3)(4)$        | $P_0=R_0=(12)(3)(4)$                                         |
| $R_1=(1)(23)(4)$        | $P_1=(R_1R_2)R_3(R_1R_2)^{-1}=(1)(3)(4)(2\bar2)$ <br />Es la reflexión en la cara opuesta al vértice 3 |
| $R_2=(1)(2)(34)$        | $P_2=R_3R_2R_3=(1)(2)(3\bar4)(4\bar3)$<br />Es el plano $R_2$ reflejado por $R_3$ |
| $R_3=(1)(2)(3)(4\bar4)$ | $P_3=R_2=(1)(2)(34)$                                         |
| $R_1R_2=(1)(243)$       |                                                              |

¿Cómo esta información nos ayuda a descubrir cuál es la bandera base del {5,3,5/2}? Cada vértice es la intersección de los tres (hiper?)planos que no llevan su nombre. Así, abusando de notación tomando $R_i:=\text{fix }R_i$,

| {3,3,5}                                 | {5,4,5/2}                     |
| --------------------------------------- | ----------------------------- |
| $v_0=R_1\cap R_2\cap R_3=1$             | $w_0=P_1\cap P_2\cap P_3=1$   |
| $v_1=R_0\cap R_2\cap R_3=\frac{1}{2}12$ | $w_1=P_0\cap P_2\cap P_3=v_1$ |
| $v_2=R_0\cap R_1\cap R_3$               | $w_2=P_0\cap P_1\cap P_3=v_1$ |
| $v_3=R_0\cap R_1\cap R_3$               | $w_3=P_0\cap P_1\cap P_2$     |



#### ¿Qué sigue?
