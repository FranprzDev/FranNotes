# Tomar Pedido Cajero

## Interfaces

### Pantalla 1
![[Pasted image 20241127012707.png]]
### Pantalla 2
![[Pasted image 20241127011349.png]]

### Pantalla 3
![[Pasted image 20241127011356.png]]

### Pantalla 4 
![[Pasted image 20241127011405.png]]
### Pantalla 5
![[Pasted image 20241127011412.png]]
**Finalizar (Local) -> f**
**Finalizar (Para Llevar) -> H** 
### Pantalla 6
![[Pasted image 20241127011417.png]]

## Desarrollo del caso de uso real:

**Caso de Uso Real:**
**Actor principal:** Cajero
**Precondiciones:**
- **Este caso de uso comienza cuando el cajero inicia un nuevo pedido.**
**Postcondiciones:**
- Pedido creado. Comanda y comprobante (ticket) generados.
**Escenario de Éxito:**
1) El cajero inicia el pedido haciendo click sobre el botón **O** de la **Pantalla 1**
2) El sistema lista en la **Pantalla 2** los rubros disponibles
3) El cajero selecciona un rubro haciendo click en el botón **A** de la **Pantalla 2**
4) El sistema lista los productos pertenecientes al rubro en la pantalla 3
5) El cajero selecciona un producto haciendo click sobre el botón **B** de la **Pantalla 3**
6) El sistema agrega el producto agrega el producto al pedido, y lista los agregados que posee en la **Pantalla 4**, con descripción y precio.  
7) El cajero selecciona sobre la **Pantalla 4** un agregado oprimiendo los botones 1-4 y confirmándolos haciendo click sobre **C**.
8) El sistema suma el agregado al producto y muestra la **Pantalla 5.**
	Se repiten los pasos 7-8 según la cantidad de agregados elegidos por el Cliente. 
	Se repiten los pasos 3-4-5-6 hasta que se indique.
9) El cajero selecciona sobre la **Pantalla 5** el botón **F** para consumir en el local el pedido.
10) El sistema registra el pedido y presenta la **Pantalla 6** con la comanda y el comprobante.
11) El cajero recibe el dinero y lo deposita en la caja
12) El cliente se dirige con la comanda a la barra para retirar su pedido
**Flujo Alternativo:**
9a) El cajero selecciona sobre la **Pantalla 5** el botón **H**  para llevar.