
## El testing normal ya se conoce
Usando arrange, act y assert se va.

## Caminos ciclomáticos
La **complejidad ciclomática** es básicamente un conteo de cuántos **caminos diferentes** existen en tu código. Para calcularlo, simplemente sigue estos pasos básicos:

1. **Cuenta cuántos `if`, `else if`, `for`, `while`, y `case` hay en tu código**. Cada uno de estos crea un "camino diferente".
2. **Suma 1 al final**. Este es el camino más básico, que ocurre si no hay condiciones.

Ejemplo:
Dado el siguiente código:

```
public String evaluarNumero(int numero) {
    if (numero > 0) { // Camino 1
        if (numero % 2 == 0) { // Camino 2
            return "Positivo y Par";
        } else { // Camino 3
            return "Positivo e Impar";
        }
    } else if (numero < 0) { // Camino 4
        return "Negativo";
    } else { // Camino 5
        return "Cero";
    }
}
```
### ¿Cómo calculamos la complejidad ciclomática?

1. **Cuenta los `if` y `else if`**:
    
    - Hay **1 `if`**: `if (numero > 0)`.
    - Hay **otro `if` dentro**: `if (numero % 2 == 0)`.
    - Hay **1 `else if`**: `else if (numero < 0)`.
    
    Total: 3 condiciones.
    
2. **Suma 1**:
    
    - 3+1=4

### ¿Qué significa esto?

Hay **4 caminos independientes**:

1. Cuando el número es positivo y par.
2. Cuando el número es positivo e impar.
3. Cuando el número es negativo.
4. Cuando el número es cero.

## Existen 2 formas de testear excepciones
- con un try catch
- con un expected

### Try - Catch
[```
@Test 
public void testMontoNegativo() {  
double montoNegativo = -1000; 
try { 
ReglaDeDescuento.calcular(montoNegativo); 
} catch (IllegalArgumentException e) {  
return; 
// Si se lanza la excepción, el test pasa. 
} 
// Si no se lanza la excepción, el test falla. [es opcional el mensaje]
throw new AssertionError("Se esperaba IllegalArgumentException para monto negativo."); 
}

### Expected
```
    @Test(expected = IllegalArgumentException.class)
    public void testMontoCero() {
        // Arrange
        double montoCero = 0;
        
        // Act
        ReglaDeDescuento.calcular(montoCero);
        
        // No Assert needed - expecting exception
    }
```
