[[Unidad 17]]

# Aplicaciones de las Integrales en Triples
## Cálculo de Volúmenes
Si definimos $f(\xi_i, \eta_i, \gamma_i) = 1$ entonces, esto no afectará al volumen de la partición de los n paralepipedos, por lo tanto podremos saber con exactitud el volumen.
Por lo tanto, efectivamente:
$$ V_R = \iiint_R dV$$
## Aplicaciones Físicas
# Masa y Peso de un Sólido de Densidad variable
Si un cuerpo tiene una densidad que varía punto a punto según los valores que toma la función $\delta = \delta(x,y,z)$ entonces:
$$ \delta(x,y,z) = \lim_{\Delta V\to0}\frac{\Delta M}{\Delta V}$$
entonces:
$$\delta(x,y,z) = \frac{dM}{dV}$$
Por lo tanto si despejamos $dM$
$$
dM = \delta(x,y,z) * dV$$
Entonces, si integramos miembro a miembro.
$$M =\iiint_R\delta(x,y,z)dV$$
Para el cálculo del peso, partimos de la definición que es la función delta por la gravedad, por lo tanto.
$$ P = g\iiint_R\delta(x,y,z)dV$$
## Momento Estático de un Sólido de Densidad Variable con respecto a los planos coordenados cartesianos

Cuando trabajamos con **alfajores triples**, hay que tener en cuenta que los momentos estáticos son en base a los planos, por lo tanto
- Con respecto al plano xy -> $dI_{xy}$
- Con respecto al plano xz -> $dI_{xz}$
- Con respecto al plano yz -> $dI_{yz}$

Por lo tanto: 
1) $dI_{xy}$ es el producto de $dM$ por la distancia "z" al plano xy.
	$dI_{xy} = zdM = z \delta(x,y,z) dV$
	Si integramos miembro a miembro:
	$I_{xy}=\iiint_Rz \delta(x,y,z) dV$
2) $dI_{xz}$ es el producto de $dM$ por la distancia "y" al plano xz.
	$dI_{xz} = ydM = y \delta(x,y,z) dV$
	Si integramos miembro a miembro:
	$I_{xz}=\iiint_Ry \delta(x,y,z) dV$
3) $dI_{yz}$ es el producto de $dM$ por la distancia "x" al plano yz.
	$dI_{yz} = xdM = x \delta(x,y,z) dV$
	Si integramos miembro a miembro:
	$I_{yz}=\iiint_Rx \delta(x,y,z) dV$

## Momentos de Inercia de un Sólido de densidad variable respecto a los planos coordenados cartesianos
En este caso de vuelta, necesitaremos los planos xy, xz, yz y en este caso las distancias estarán al cuadrado.

Por lo tanto: 
1) $dJ_{xy}$ es el producto de $dM$ por la distancia "$z^2$" al plano xy.
	$dJ_{xy} = z^2dM = z^2 \delta(x,y,z) dV$
	Si integramos miembro a miembro:
	$J_{xy}=\iiint_Rz^2 \delta(x,y,z) dV$
2) $dJ_{xz}$ es el producto de $dM$ por la distancia "$y^2$" al plano xz.
	$dJ_{xz} = y^2dM = y^2 \delta(x,y,z) dV$
	Si integramos miembro a miembro:
	$J_{xz}=\iiint_Ry^2 \delta(x,y,z) dV$
3) $dJ_{yz}$ es el producto de $dM$ por la distancia "$x^2$" al plano yz.
	$dJ_{yz} = x^2dM = x^2 \delta(x,y,z) dV$
	Si integramos miembro a miembro:
	$J_{yz}=\iiint_Rx^2 \delta(x,y,z) dV$

## Coordenadas del centro de masa de un sólido de densidad variable
Como ya sabemos, los momentos estáticos respecto a los planos son 0.
Por lo tanto entonces:

**Si trabajamos con $I_{yz} = 0$**
$$\iiint_R(x-x_c)\delta(x,y,z)dV=0$$
Por propiedad de las integrales ( separamos y sacamos la constante)
$$
\iiint_Rx\delta(x,y,z)dV-x_c\iiint_R\delta(x,y,z)dV=0
$$
Como lo que queremos saber es $x_c$ lo despejamos
$$
x_c = \frac{\iiint_Rx\delta(x,y,z)dV}{\iiint_R\delta(x,y,z)dV}
$$
Donde precisamente lo de abajo es la masa y lo de arriba es $I_{yz}$, es decir:
$$
x_c = \frac{I_{yz}}{M}
$$
**Si trabajamos con $I_{xz}$** (mismo procedimiento)
$$\iiint_R(y-y_c)\delta(x,y,z)dV=0$$
Por propiedad de las integrales ( separamos y sacamos la constante)
$$
\iiint_Ry\delta(x,y,z)dV-y_c\iiint_R\delta(x,y,z)dV=0
$$
Como lo que queremos saber es $y_c$ lo despejamos
$$
y_c = \frac{\iiint_Ry\delta(x,y,z)dV}{\iiint_R\delta(x,y,z)dV}
$$
Donde precisamente lo de abajo es la masa y lo de arriba es $I_{xz}$, es decir:
$$
y_c = \frac{I_{xz}}{M}
$$
**Si trabajamos con $I_{xy}$** (mismo procedimiento)
$$\iiint_R(z-z_c)\delta(x,y,z)dV=0$$
Por propiedad de las integrales ( separamos y sacamos la constante)
$$
\iiint_Rz\delta(x,y,z)dV-z_c\iiint_R\delta(x,y,z)dV
$$
Como lo que queremos saber es $z_c$ lo despejamos
$$
z_c = \frac{\iiint_Rz\delta(x,y,z)dV}{\iiint_R\delta(x,y,z)dV}
$$
Donde precisamente lo de abajo es la masa y lo de arriba es $I_{xz}$, es decir:
$$
z_c = \frac{I_{xy}}{M}
$$