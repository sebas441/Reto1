## Reto de Programación Unidad 3    

## Sistema de Monitoreo de Vuelo para un Cohete Suborbital    
  
### **Contexto de Ingeniería:**    
  
Un equipo de pruebas aeroespaciales requiere un software para monitorear en consola el ascenso y descenso de un cohete suborbital experimental. El programa debe procesar  
las lecturas de los sensores tiempo a tiempo ($t = 0, 1, 2, ...$ segundos) ingresadas por el operador o generadas por un ciclo de simulación, evaluando el estado del vehículo en cada segundo sin almacenar el historial completo en memoria.    

### Módulos del Software y Temas Evaluados  

El programa debe construirse aplicando **programación modular (funciones)**, evitando el uso de variables globales y utilizando únicamente tipos de datos primitivos (`float`, `int`, `bool`, `str`).  

**1. Análisis del Problema y Representación (Fase de Diseño prioritaria)**   
 
Antes de tocar el teclado para programar, los estudiantes deben entregar:    

- **Análisis E/P/S:** Identificación clara de datos de entrada (presión en $hPa$, aceleración en $m/s^2$, temperatura en $°C$), procesos matemáticos/lógicos y datos de salida requeridos.    
- **Diagrama de Flujo y Pseudocódigo:** Diagrama completo del ciclo principal y pseudocódigo detallado de cada función.   

**2. Funciones Matemáticas y Lógicas (Uso de Funciones y Condicionales)**   

Deben implementar al menos tres funciones independientes:  

- `calcular_altitud(presion_hpa)`: Recibe la presión atmosférica y retorna la altitud en metros mediante la fórmula barométrica:      
    
    $h = 44330 \times \left( 1 - \left( \frac{P}{1013.25} \right)^{0.1903} \right)$  
    
- `determinar_estado_vuelo(altitud_actual, altitud_previa, aceleracion)`: Retorna un código o texto que indica la fase del cohete: `1: Ascenso`, `2: Apogeo / Caída libre`, `3: Despliegue de Paracaídas`.  
- `evaluar_alerta_temperatura(temp_celsius)`: Evalúa si la temperatura del motor o la estructura supera límites críticos e indica si se debe emitir una alarma.  

**3. Ciclo de Control de Vuelo (Uso de Bucles, Acumuladores y Banderas)**  

El programa principal debe ejecutar un bucle que simule o solicite datos segundo a segundo hasta que el cohete aterrice (altitud $\le 0$) o el operador finalice la simulación:  

- **Cálculo de Apogeo (Máximo):** Usar una variable escalar para conservar la altitud máxima alcanzada.  
- **Detección del Apogeo:** Usar condicionales para detectar cuando `altitud_actual < altitud_previa` por primera vez (bandera booleana).  
- **Estadísticas en Tiempo Real:** Calcular la temperatura promedio y la aceleración máxima mediante variables acumuladoras y contadores (sin guardar los datos en listas).  
