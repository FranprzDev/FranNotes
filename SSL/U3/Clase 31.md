## Simplificaciones de una GIC
Para obtener la FNC como la FNG de una GIC, se necesita en primer lugar simplificar la gramática eliminando reglas indeseables.

Los pasos a seguir son
1) Eliminar las reglas innecesarias
	Son producciones que no aportan nada, no cumplen con:
	$S \Rightarrow^* \space \alpha N \beta \space y \space N \Rightarrow^* \space w$
	Donde S es el axioma, $w \in \Sigma_T^*$ y $\alpha, \beta \in \Sigma^*$ 
	Reglas de la forma: $N \rightarrow N$ (Redenominación)
2) Considerar la generación de la palabra vacía
	Si $S \rightarrow^* \lambda$, entonces
	- Si el axioma no figura a la derecha se agrega la regla $S \rightarrow \lambda$ 
	- Caso contrario, si el axioma aparece a la derecha de alguna de las reglas de producción se debe realizar el siguiente artificio.
		1) Se introduce un nuevo simbolo $S_1$ 
		2) Se agregan las producciones de las reglas: $S_1 \rightarrow S \space | \space \lambda$ 
3) Eliminar las reglas de borrado $N \rightarrow \lambda$
	Partimos de una $GIC = < \Sigma_N, \Sigma_T, S, P>$
	1) Identificamos el conjunto A de los no-terminales anulables, es decir todos aquellos que cumplan con $N \Rightarrow^* \lambda$ 
		1) Inicializamos A con todos los no-terminales N para los cuales existe una producción de borrado, excepto para el propio axioma.
		2) Para cada $N \rightarrow W \in P$, Si $W \in A^+$ entonces agregar N a A.
	2) Se reemplaza las producciones de la forma $N \rightarrow \lambda$ por las reglas que surgen de sustituir los no-terminales anulables por $\lambda$, en todas las reglas que figuren exceptuando las de borrados. Si $\lambda$ pertenece a la GIC, la única regla de borrado que no debe eliminarse es cuando el axioma deriva a lambda 
4) Eliminar reglas de redenominación del tipo $N_1 \rightarrow N_2$
	Partimos de una $GIC = < \Sigma_N, \Sigma_T, S, P>$ que no tiene reglas de borrado


## Obtención de la Forma Normal de Chomsky para una GIC (FNC)
Debemos seguir los siguientes pasos:
1) **Obtener la GIC simplificada o bien formada:** Eliminar las reglas innecesarias, de borrado y de redenominación
2) **Llevar a la GIC al FNC de tipo 0** Es decir, sustituir los terminales de la parte derecha por nuevos no-terminales y se agregan las reglas **nuevo no-terminal** derivada a **terminal asociado**
3) **Reducción de la longitud** Para toda regla que no cumpla con el FNC de tipo 2, se procede a reducir la longitud mediante sustituciones, agregando los no-terminales nuevos que sean necesarios.