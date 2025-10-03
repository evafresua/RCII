### Modulación por Codificación de Impulsos (PCM)

- **Teorema del muestreo:** Si una señal es muestreada a intervalos regulares a una velocidad al menos el doble de su componente de mayor frecuencia, estas muestras contienen la misma información que la señal original.
- **La voz está limitada a 4000 Hz**, por tanto se requieren **8000 muestras por segundo**.
- Las muestras analógicas reciben el nombre de **PAM (Pulsos Modulados en Amplitud)**, y a cada PAM se le asigna un valor digital.
- Una digitalización de **4 bits proporciona 16 niveles**.
- **Error o ruido de cuantización:** Cada bit adicional mejora la relación señal/ruido (S/N) en **6 dB**, es decir, un factor de 4.

---

### Cuanti


¿Quieres que te lo convierta en un esquema visual o en tarjetas de repaso para memorizar los conceptos clave? 🎓zación no lineal

- El error de cuantización es mayor en muestras de pequeña amplitud, por tanto los elementos pequeños están, en términos relativos, más distorsionados.
- Puede mejorarse la cuantización usando un número mayor de niveles para señales de poca amplitud y un número menor para señales de gran amplitud.
- También se puede hacer con una función de compresión y una cuantización lineal.
- En voz, estas mejoras pueden alcanzar entre **24 y 30 dB**.

---

### Modulación Delta (DM)

- Una señal analógica es aproximada por una función escalera.
- Se sube o se baja un nivel en cada intervalo de muestreo. La transición hacia arriba o hacia abajo se elige de tal forma que la función escalera aproxime de la mejor forma la señal original.
- La salida de la modulación Delta se puede representar como **un único bit por cada muestra**.
- Parámetros importantes:
    - **Cuanto de amplitud** (ruido de cuantización): tamaño del escalón.
    - **Frecuencia de muestreo** (ruido de sobrecarga de pendiente).
- Implementación muy sencilla.

---

### Prestaciones de la transmisión digital de señales analógicas en la transmisión de voz

- Una buena calidad se puede conseguir con **PCM de 128 niveles**, es decir, con **7 bits**.
- Partiendo de voz con ancho de banda de 4 kHz, se necesitan **56 kbps para PCM**.  
    (4 kHz → por Nyquist → 8000 muestras/segundo → 8000 × 7 bits = 56 kbps)
- Si el PCM viaja mediante un esquema **AMI bipolar** (o cualquier codificación de 2 símbolos), se necesitarían **28 kHz de ancho de banda**, pero tiene ventajas:
    - No hay ruido aditivo.
    - No se usa FDM (modulación por división de frecuencia), sino **TDM (modulación por división en el tiempo)**.
    - Posibilidad de conmutaciones de forma más sencilla.
- Se pueden usar técnicas de compresión.  
    Por ejemplo, en imágenes se puede reducir de **92 Mbps** (el color de cada punto se codifica con 10 bits) a **15 Mbps**.  
    En secuencias que varíen poco, hasta **64 kbps**.
