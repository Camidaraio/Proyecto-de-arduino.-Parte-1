### Proyecto en Arduino

------------

#### Integrantes

------------
- Daraio Camila.
- Dominguez Franco.

 
#### Proyecto contador Binario.

------------

imagen de la parte 1

####  Descripcion

------------


Diseñamos un contador de 0 a 99 utilizando dos displays de 7 segmentos y tres botones para controlar la cuenta. Implementamos la técnica de multiplexación para mostrar los dígitos en los displays. El contador comienza en 0  y  es capaz de aumentar o disminuir su valor en una unidad con los botones.

------------


####  Funcion principal

------------


La principal finalidad de este proyecto es operar un visualizador de 7 segmentos mediante tres botones conectados a una placa Arduino. Cada uno de estos botones tiene un propósito específico:

1. **Botón de Aumento (Botón 4):** Incrementa el contador, permitiendo un máximo de 99 como valor.
2. **Botón de Disminución (Botón 3):** Reduce el contador.
3. **Botón de Reinicio (Botón 5):** Restablece el contador a la posición 0.

Para lograr esta interacción, se utilizan las directivas `#define` para asignar nombres descriptivos a los pines y constantes asociados:

- Se definen los pines del visualizador de 7 segmentos (B13, A12, F11, G10, E9, D8, C7) para simplificar la conexión.
- Los pines de los botones (SUBE, BAJA, RESET) se asignan a pines específicos de la placa Arduino (4, 3, 5).
- Los pines UNIDAD (A4) y DECENA (A5) se emplean para conectar las unidades y decenas del visualizador.
- APAGADOS (0) se utiliza para apagar todos los segmentos del visualizador.
- TIMEDISPLAYON (10) regula la duración de visualización de cada número en el display.

En resumen, este proyecto ofrece la posibilidad de interactuar con un contador mediante botones, mostrando su valor en un visualizador de 7 segmentos. 

```cpp

void prendeDigito(int digito)
{
	if(digito == UNIDAD)
    {
    	digitalWrite(UNIDAD, LOW);
        digitalWrite(DECENA, HIGH);
		delay(TIMEDISPLAYON);
    }
  	else if(digito == DECENA)
    {
    	digitalWrite(UNIDAD, HIGH);
        digitalWrite(DECENA, LOW);
		delay(TIMEDISPLAYON);
    }
  	else
    {
    	digitalWrite(UNIDAD, HIGH);
        digitalWrite(DECENA, HIGH);

    }
  
  
}
```










