Inicio  
Definir alt_act, alt_previa (con float)  
Definir presión, aceleración, temperatura (como float)  
Definir alt_max (como float = 0)  
Definir suma_temp (como float = 0)   
Definir contador (int) = 0  
Definir max_aceleración (float = 0)  
Definir apogeo_detec (como booleano = FALSO)                         
                           
Mientras sea VERDADERO            
Leer presión             
Leer aceleración            
Leer temperatura                              
# Calcular altitud                     
alt_act = calcular_altitud (presión)                             
# Determinar el estado                        
estado = determine_estado_vuelo(alt_actual, alt_previa, aceleración)               
alerta = evaluar_alerta_temperatura(temperatura)                  
si alt_act > alt_max entonces                    
   alt_max = alt_act                        
fin si                        
si alt_act < alt_previa y apogeo_dect == falso entonces                   
   apogeo_dect = verdadero                 
fin si                
suma_temp = suma_temp + temperatura                            
contador += 1 o contador = contador + 1                       
sí aceleración > max_aceleración entonces                 
   max_aceleración = aceleración               
fin si             
imprimir (alt_act, estado, alerta)              
sí alt_act  < 0 entonces             
   romper           
fin si              
alt_previa = alt_act             
fin mientras                           
promedio_temperatura = suma_temp / contador                                       
imprimir (alt_max, promedio_temperatura, max_acelaración)                           
fin                 


función calcular_alt(presión)                       
  retornar 44330 * (1 - (presión / 1013,25)^0.1903              
fin función                   
función determinar_estado_vuelo(actual"act", previa, aceleración)                     
  sí act > previa entonces                     
    retornar "ascenso"             
  sino              
    retornar (apogeo/caída)                
  fin si             
fin función                           
función evaluar_alerta_temperatura(temperatura)              
sí temperatura > 100 entonces                    
  retornar (alerta)                           
sino                
  retornar (normal)                
fin si           
fin función        
