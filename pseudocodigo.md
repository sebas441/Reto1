Inicio                         
FUNCIÓN calcular_altitud(presion_hpa)                     
    RETORNAR 44330 * (1 - (presion_hpa / 1013.25) ^ 0.1903)                     
FIN FUNCIÓN                         


FUNCIÓN determinar_estado_vuelo(alt_actual, alt_previa, aceleracion, apogeo_detectado)                                      

    SI aceleracion < 0 Y alt_actual > alt_previa ENTONCES                        
        RETORNAR "Ascenso por inercia"                             
                           
    SINO SI alt_actual > alt_previa ENTONCES                   
        RETORNAR "Ascenso"                     

    SINO SI alt_actual < alt_previa Y apogeo_detectado = FALSO ENTONCES                      
        RETORNAR "Apogeo"                           

    SINO SI alt_actual < alt_previa Y apogeo_detectado = VERDADERO ENTONCES               
        RETORNAR "Caída libre"                                

    SINO                         
        RETORNAR "Estable"                 
FIN FUNCIÓN                
              

FUNCIÓN evaluar_alerta_temperatura(temp)                  
    SI temp > 100 ENTONCES                  
        RETORNAR "ALERTA"                 
    SINO                 
        RETORNAR "Normal"                   
FIN FUNCIÓN                  


FUNCIÓN main()                           

    alt_previa = 0                                            
    alt_max = 0                                   
    suma_temp = 0               
    contador = 0              
    max_aceleracion = 0                   
    apogeo_detectado = FALSO                  

    MIENTRAS VERDADERO                  

        LEER entrada               

        SI entrada = "salir" ENTONCES                                  
            MOSTRAR "Fin manual"                    
            SALIR DEL BUCLE           
        FIN SI                  

        INTENTAR                            
            presion = convertir a número              
            aceleracion = convertir a número                
            temp = convertir a número               
        SI ERROR              
            MOSTRAR "error de datos"              
            CONTINUAR               
        FIN INTENTAR                 

        alt_actual = calcular_altitud(presion)                      
        estado = determinar_estado_vuelo(alt_actual, alt_previa, aceleracion, apogeo_detectado)                
        alerta = evaluar_alerta_temperatura(temp)                      

        SI alt_actual > alt_max ENTONCES                                      
            alt_max = alt_actual           
        FIN SI                 

        SI alt_actual < alt_previa Y apogeo_detectado = FALSO ENTONCES                    
            apogeo_detectado = VERDADERO                   
        FIN SI                    

        suma_temp = suma_temp + temp                       
        contador = contador + 1                

        SI aceleracion > max_aceleracion ENTONCES                  
            max_aceleracion = aceleracion              
        FIN SI                   

        MOSTRAR alt_actual                
        MOSTRAR estado              
        MOSTRAR alerta            

        SI alt_actual <= 1 Y contador > 1 ENTONCES                                             
            MOSTRAR "buen aterrizaje"           
            SALIR DEL BUCLE                
        FIN SI            

        alt_previa = alt_actual              

    FIN MIENTRAS              

    SI contador > 0 ENTONCES                        
        promedio_temp = suma_temp / contador              
    SINO             
        promedio_temp = 0             
    FIN SI            

    MOSTRAR alt_max              
    MOSTRAR promedio_temp             
    MOSTRAR max_aceleracion            

FIN FUNCIÓN                    


LLAMAR main()                         
Fin                  
