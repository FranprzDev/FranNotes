# FNG
$$
N \rightarrow tW
$$
Con:
- $N \in \Sigma_N$
- $t \in \Sigma_T$
- $W \in \Sigma_N^*$
- Como excepción $S \rightarrow \lambda$, pero sin S a la derecha.

## Pasos para obtener la FNG
1) **Obtener la GIC simplificada,** eliminar las reglas innecesarias, de borrado y de redenominación
2) **Eliminar reglas recursivas por izquierda** Es decir reglas de la forma $N \rightarrow N \beta$ (recursividad directas) o reglas que conducen a una recursividad por izquierda en varios pasos, es decir $N \Rightarrow^* N \beta$ 
3) **Eliminación de reglas que comiencen con no-terminal** A efectos que todas las reglas comiencen con un terminal, se debe realizar una serie de sustituciones.
4) **Sustitución de sufijos con terminales** Con el fin de llegar a la FNG se transforma las reglas que tengan a la derecha sufijos con terminales.

## Eliminación de recursividades por izquierda

Para eliminar las recursividades por izquierda se reemplaza las reglas de la forma:
$$
	N \rightarrow N \alpha_1 \space  | \space N \alpha_2 \space | \space  \dots \space | \space  N \alpha_n \space | \space \beta_1  \space | \space  \beta_2 \space  | \space  \dots \space | \space  \beta_m
$$
Por las siguientes reglas equivalentes
$$
N \rightarrow \beta_1N' \space | \space \beta_2N' \space | \space \dots \space | \space \beta_mN'
$$
$$N \rightarrow \alpha_1N' \space | \space \alpha_2N' \space | \space \dots \space | \space \alpha_nN \space | \space \lambda'$$

Para realizar este proceso de forma sistemática se parte de una gramática simplificada, sin recursividades  por izquierda y se siguen los siguientes pasos:
1) Establecer un orden cualquiera para los No-Terminales $N_1,N_2,\dots, N_n$ 
2) Dividir las reglas en 3 grupos:
	1) Grupo 1: $N_i \rightarrow xw \space | \space x \in \Sigma_T, w \in \Sigma^*$ 
	2) Grupo 2: $N_i \rightarrow N_jw \space | \space$  $N_i, N_j \in \Sigma_N, i < j, w \in \Sigma^*$
	3) Grupo 3: $N_i \rightarrow N_jw \space | \space N_i, N_j \in \Sigma_N, i > j, w \in \Sigma^*$
3) Seleccionar las reglas del grupo 3 cuyo "i" sea mínimo en el orden y se las sustituye por las que se obtiene al reemplazar $N_j$ por todas las partes derechas de sus producciones; repitiendo esta regla.

**Sustitución de sufijos con terminales**
Se parte de una GIC, cuyas reglas en sus partes derechas comienzan con un símbolo terminal a excepción de la regla de borrado, si es que existe. 
Para cada relga que no cumpla con la FNG, ya que en su parte derecha tiene más de un terminal se reemplaza cada terminal, menos el primero por un nuevo no-terminal y luego se agrega la regla "nuevo no-terminal" deriva al terminal asociado.

## Factorización por Izquierda
Cuando en una GIC tenemos para un mismo no-terminal, reglas que tienen partes derechas con prefijos iguales; se produce una indeterminación en el momento de elegir una de esas reglas para resolver el problema de análisis de una palabra.
El proceso que elimina este problema se denomina factorización por la izquierda y se define como:
- Por cada $N \in \Sigma_N$ 
	- Si $N \rightarrow \beta \alpha_1 \space | \space \beta \alpha_2 \space | \space \dots \space | \space \beta \alpha_k$
	- Entonces se cambian las producciones por:
		- $N \rightarrow \beta N'$
		- $N' \rightarrow \alpha_1 | \alpha_2 | \dots | \alpha_k$


