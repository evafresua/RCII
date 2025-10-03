Es necesario controlar:

- Los **errores de transmisión**
- La **velocidad de recepción**
----

## Control de flujo

- **Parada y espera**
- **Ventana deslizante**
---
##  Detección de errores

- **Comprobación de paridad**
- **Comprobación de redundancia cíclica (CRC)**
    - Es un procedimiento de aritmética binaria.
    - En Europa se usa **CRC-CCITT**.
---
##  Control de errores

- **Gama ARQ (Automatic Repeat reQuest)**
    - ARQ parada y espera
    - ARQ vuelta atrás-N
    - ARQ rechazo selectivo  
        _(Ambos aplicables a ventana deslizante)_

---

##  HDLC (High-Level Data Link Control)

- Muy usado y el más importante.
    
- Define:
    
    - **3 tipos de estaciones:**
        - Primaria
        - Secundaria
        - Combinada
    - **2 configuraciones del lenguaje:**
        - No balanceada (1 primaria, 2 o más secundarias)
        - Balanceada (2 o más combinadas)
    - **3 modos de operación:**
        - NRM (Modo de Respuesta Normal)
        - ABM (Modo Balanceado Asíncrono)
        - ARM (Modo de Respuesta Asíncrono)
- Es **síncrono**, por lo que utiliza **tramas** para los intercambios.  
    _(Así puede delimitar el comienzo y fin de cada trama)_
    

---

### Estructura de trama HDLC

- **Flag** = delimitador → `01111110`
- **Dirección:** habitualmente 8 bits, pero puede extenderse a múltiplos de 7 bits tras negociación.  
    _(En enlaces punto a punto no es necesario, pero se usa para uniformizar el protocolo)_
- **Control:** informa del tipo de paquete, especialmente sobre ARQ de errores y flujo (número de secuencia).
- **FCS (Frame Check Sequence):** comprobación de trama.

---

##  Otros protocolos 

- **LAPB:** Balanceado, ABM, usado en Frame Relay.
    
- **LAPD:** Controla el canal D de RDSI, ABM.
    
- **LLC (Logical Link Control):**
    
    - Usado en LANs.
    - No existe el concepto de estación primaria/secundaria.
    - No usa todo HDLC, añade otras características.
    - Tiene dos subcapas:
        - **MAC (Media Access Control)**
        - **LLC (Logical Link Control)**
- **LAPF:** Usado en Frame Relay, ABM.
    
- **ATM:** No basado en HDLC. El resto sí.
    
