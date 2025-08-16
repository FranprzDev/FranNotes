## Como hacer un rebase y no morir en el intento

![[Pasted image 20250707103002.png]]

Utilizamos rebase cuando queremos ponernos al corriente de la rama poniendo nuestros cambios después de los cambios de los demás. Es decir, no escribimos por encima de el flujo normal, si no; que nos colocamos al final y agregamos una **"copia"** de nuestros commits.

## Situaciones
### Situación típica
Estuve trabajando en la rama ```feat/something``` y hay otra persona que estuvo trabajando en `feat/something2`, y resulta que la segunda rama fue mergeada primero, en ese caso lo que hay que hacer es lo siguiente (paso a paso)

1) Asegurarme tener todos los cambios con commits en `feat/something`
		**Importante:** es mucho más fácil, hacer un commit que hacer un stash o alguna otra cosa rara.
2) Pasarse a la rama principal de donde se aprobó el pull request de `feat/something2`
		**Importante:** En la mayoría de los casos suele ser **dev**, y en el caso de LABS es así. 
3) Traerse los cambios en esta rama, para que tengamos actualizados los cambios
		**Comando:** git pull origin dev
4) Pasarse a la rama que queremos mergear (`feat/something`)
5) Ejecutar el comando: **git rebase dev**
6) **Rogar por que no existan conflictos**
	1) En el caso de no existir los conflictos, ya se puede proceder a enviar el pull request con el siguiente comando `git push origin feat/something --force` 
			**IMPORTANTE:** El --force lo fuerza (como dice su nombre), así que utilizarlo con precaución, con esto se actualiza el historial de commits de la rama, haciendo que coincida con la principal (en este caso dev), y ya se puede hacer el pull request de forma correcta.
	2) Si se da la casualidad de que existen conflictos se deben resolver los conflictos.
		- Habrán tantas resoluciones de conflictos como commits, el propio VSC te dirá cuantos commits hay, si hay 10 commits, no necesariamente los 10 commits igual tendrán problemas; capaz que son 5 de los 10 y los otros sucede lo del paso 1.
		- Es importante cuidar no romper nada entre lo que se acepta un código y el otro, es cuestión de cancha, pero se puede ir probando y probando hasta que te des cuenta cual es el código correcto.
		- Capaz que lo ideal sería aceptar ambos códigos y probarlo, comentar uno y después el otro hasta encontrar el problema. 
7) Si llega a suceder el caso que hubo un error, lo más fácil es usar `git rebase --abort` y volver a empezar.

### Recomendaciones
Cada vez que se envie un nuevo PR a la rama de origen (dev), intentar actualizarse constantemente, de esta forma no habrá que resolver conflictos, o si los hay que resolver como mucho son de 1 commit. 
