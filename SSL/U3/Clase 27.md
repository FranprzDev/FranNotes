# Gramáticas independientes del Contexto (GIC)
Definimos a una GIC como:
$$
GIC = <\Sigma_N, \Sigma_T, P, S>
$$
Las reglas de P pueden ser:
$$
N \rightarrow \beta
$$
Donde: $N \in \Sigma_N \space y \space \beta \in (\Sigma_N \cup \Sigma_T)^*$ 

El lenguaje, es el independiente del contexto que pertenece a las gramáticas del tipo 2 según la Jerarquía de Chomsky, y pertenece al nivel sintáctico; el modelo que lo representa es el **automata de pila**

## Diseño de una GIC
Para construir una GIC a partir de un LIC se recurre a distintos artificios.
1) Adaptación de una gramática
	Se pueden realizar modificaciones sencillas a una gramática conocida para obtener la del lenguaje requerido, no hay una forma como tal para hacer esto, si no que consiste en darse cuenta y ser pillo.
	El ejemplo que se proporciona es el siguiente:
	![[Pasted image 20250724015822.png]]
	Dado esto, si queremos generar una nueva $LIC$ que cumpla que:
	$LIC8 = \{a^nb^m / n,m \geq 0 \space y \space n > m\}$
	Entonces lo que debemos hacer es pensar donde poner las reglas, el ejemplo sugiere lo siguiente:
	![[Pasted image 20250724020059.png]]
2) Mezcla de Gramáticas
	Podemos combinar dos gramáticas, de manera que la gramática resultante contenga la unión de todas las reglas de ambas gramáticas, para esto se debe tener en cuenta los simbolos terminales y no terminales, y que el axioma debe ser el mismo pero mezclandolo.
	![[Pasted image 20250724023912.png]]
3) Operaciones con GIC
	1) Unión
		Dada $G_1=<\Sigma_{N_1}, \Sigma_{T_1},S_1,P_1>$ y $G_2=<\Sigma_{N_2}, \Sigma_{T_2},S_2,P_2>$
		La unión será aquella que genere una nueva gramática, $G_3$ tal que $L(G_3) = L(G_1) \cup L(G_2)$ Por lo tanto, para $G_3$ será la unión del alfabeto de no terminales y la unión del alfabeto de terminales, además de la unión de las reglas de producción agregando una nueva regla de producción, $S_3$ que será la unión de los axiomas de cada GR, es decir $S_3 = S_1 \cup S_2$
		![[Pasted image 20250724024608.png]]
	2) Concatenación
		Dada $G_1=<\Sigma_{N_1}, \Sigma_{T_1},S_1,P_1>$ y $G_2=<\Sigma_{N_2}, \Sigma_{T_2},S_2,P_2>$ se generará una  $G_3=<\Sigma_{N_3}, \Sigma_{T_3},S_3,P_3>$ siendo la concatenación de $L(G_3) = L(G_1).L(G_2)$ 
		Donde:
		$\Sigma_{N3}=\Sigma_{N1}\cup\Sigma_{N2} \cup \{S_3\}$
		$\Sigma_{T3}=\Sigma_{T1}\cup \Sigma_{T2}$
		$P_3=P_1\cup P_2\cup { S_3 \rightarrow S_1S_2 }$ 
	3) Estrella de Kleene
		Dada $G_1=<\Sigma_{N_1}, \Sigma_{T_1},S_1,P_1>$ Definimos una nueva $G_3=<\Sigma_{N_3}, \Sigma_{T_3},S_3,P_3>$ donde $L(G3)=L(G1)^*$
		Donde:
		$\Sigma_{N3}=\Sigma_{N1} \cup \{S_3\}$
		$\Sigma_{T3}=\Sigma_{T1}
		$P_3=P_1\cup { S_3 \rightarrow S_1S_3 | \lambda }$ 
	4) Estrella Positiva
		Dada $G_1=<\Sigma_{N_1}, \Sigma_{T_1},S_1,P_1>$ Definimos una nueva $G_3=<\Sigma_{N_3}, \Sigma_{T_3},S_3,P_3>$ donde $L(G3)=L(G1)^+$
		Donde:
		$\Sigma_{N3}=\Sigma_{N1} \cup \{S_3\}$
		$\Sigma_{T3}=\Sigma_{T1}$
		$P_3=P_1\cup { S_3 \rightarrow S_1S_3 | S_1 }$ 
	5) Inversa
		Dada $G_1=<\Sigma_{N_1}, \Sigma_{T_1},S_1,P_1>$ Definimos una nueva $G_3=<\Sigma_{N_3}, \Sigma_{T_3},S_3,P_3>$ donde $L(G3)=L(G1)^-1$
		Donde:
		$\Sigma_{N3}=\Sigma_{N1}$
		$\Sigma_{T3}=\Sigma_{T1}$
		$P_3= N \rightarrow \beta^-1 / N \rightarrow \beta \in P_1$
		 
