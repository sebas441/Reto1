INICIO                       

Definir           
altitud_previa = 0            
altitud_max = 0            
suma_temp = 0     
contador = 0  
max_aceleracion = 0                        
apogeo_detectado = falso                    

MIENTRAS verdadero           
    Leer presión, aceleración, temperatura              

    altitud_actual = calcular_altitud  (presión)                               
    estado = determinar_estado_vuelo                
    alerta = evaluar_alerta_temperatura                 

    SI altitud_actual > altitud_max              
        actualizar altitud_max               

    SI altitud_actual < altitud_previa Y no apogeo                
        activar apogeo         

    acumular temperatura        
    aumentar contador           

    SI aceleración > máxima           
        actualizar             
          
    Mostrar datos                                                                              
                                  
    SI altitud_actual <= 0            
        salir                   

    altitud_previa = altitud_actual             

FIN MIENTRAS             
                  
Calcular promedio               
Mostrar resultados                 

FIN           
