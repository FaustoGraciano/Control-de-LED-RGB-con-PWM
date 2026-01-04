# Control de LED RGB con PWM

## 📌 Descripción
Este proyecto consiste en el control de la **intensidad y el color de un LED RGB** mediante la técnica de **modulación por ancho de pulso (PWM)** utilizando un microcontrolador **ATmega328P**.

El sistema permite seleccionar qué color del LED (Rojo, Verde o Azul) se desea modificar a través de la **interfaz serie UART**, y ajustar su brillo en tiempo real usando un **potenciómetro** conectado a una entrada analógica. La combinación de los tres canales PWM permite obtener distintos colores resultantes.

El proyecto fue desarrollado y probado en el entorno de simulación **Proteus**.

---

## ▶️ Cómo ejecutar el programa
1. Abrir el proyecto en **Proteus**.
2. Cargar el archivo `.hex` generado a partir del código en C en el **ATmega328P**.
3. Iniciar la simulación.
4. Abrir la **Terminal Virtual (UART)** para interactuar con el sistema.

---

## 🕹️ Cómo usar el sistema
1. Enviar un carácter por la UART para seleccionar el color a modificar:
   - **`R`** → Rojo  
   - **`G`** → Verde  
   - **`B`** → Azul
2. Girar el **potenciómetro** para ajustar la intensidad del color seleccionado (valores de 0 a 255).
3. Presionar **`E`** para confirmar el valor y evitar que siga modificándose.
4. Repetir el proceso para los otros colores si se desea.
5. El color final del LED resulta de la combinación de las intensidades RGB.

---

## ⚙️ Implementación (resumen técnico)
- **Microcontrolador:** ATmega328P
- **Periféricos utilizados:**
  - LED **RGB ánodo común**
  - **Potenciómetro** (ADC3)
  - **UART0** (Terminal Virtual en Proteus)
- **Lenguaje:** C
- **PWM:**
  - Rojo: PWM por software usando **Timer0**
  - Verde y Azul: PWM por hardware usando **Timer1 (Fast PWM 8 bits)**
- **ADC:**
  - Lectura analógica del potenciómetro
  - Resolución de 8 bits (uso de ADCH)
- **UART:**
  - Recepción de comandos por interrupción
  - Selección dinámica del color a modificar
- **Frecuencia PWM:** ≥ 50 Hz

---

## 📚 Contexto académico
Trabajo Práctico N.º 4  
**Circuitos Digitales y Microcontroladores – UNLP**

---

## 📄 Licencia
Este proyecto se distribuye bajo la **MIT License**.
