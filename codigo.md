def calcular_altitud(presion_hpa):          
    return 44330 * (1 - (presion_hpa / 1013.25) ** 0.1903)               


def determinar_estado_vuelo(alt_actual, alt_previa, aceleracion, apogeo_detectado):                   
    if aceleracion < 0 and alt_actual > alt_previa:                       
        return "Ascenso por inercia"                
    elif alt_actual > alt_previa:                
        return "Ascenso"                 
    elif alt_actual < alt_previa and not apogeo_detectado:                   
        return "Apogeo"                 
    elif alt_actual < alt_previa and apogeo_detectado:                   
        return "Caída libre"                      
    else:               
        return "Estable"                 

def evaluar_alerta_temperatura(temp):                 
    return "ALERTA" if temp > 100 else "Normal"                                                  

def main():                    

    alt_previa = 0                 
    alt_max = 0                   
    suma_temp = 0                  
    contador = 0                  
    max_aceleracion = 0                
    apogeo_detectado = False                     

    while True:                       

        entrada = input("\nPresión o salir: ")                                      

        if entrada.lower() == "salir":            
            print("Fin manual")               
            break                  

        try:                    
            presion = float(entrada)                     
            aceleracion = float(input("Aceleración: "))                 
            temp = float(input("Temperatura: "))                   
        except:                     
            print("error de tus datos dados")                                         
            continue                 

        alt_actual = calcular_altitud(presion)                    

        estado = determinar_estado_vuelo(                         
            alt_actual, alt_previa, aceleracion, apogeo_detectado                
        )                                        

        alerta = evaluar_alerta_temperatura(temp)                

        if alt_actual > alt_max:             
            alt_max = alt_actual                   

        if alt_actual < alt_previa and not apogeo_detectado:                 
            apogeo_detectado = True                 
             
        suma_temp += temp                   
        contador += 1                

        if aceleracion > max_aceleracion:              
            max_aceleracion = aceleracion                                 

        print("\nAltitud:", round(alt_actual, 2))                                  
        print("Estado:", estado)                  
        print("temperatura:", alerta)                   
             
        if alt_actual <= 1 and contador > 1:                 
            print("\nQue buen aterrizaje, ¿aterrizaje verdad?")               
            break                    

        alt_previa = alt_actual                                 

               
    if contador > 0:                                         
        promedio_temp = suma_temp / contador                      
    else:              
        promedio_temp = 0                           

    print("\nRESULTADOS")                             
    print("Altitud máxima:", round(alt_max, 2))                 
    print("Temperatura promedio:", round(promedio_temp, 2))              
    print("Aceleración máxima:", round(max_aceleracion, 2))                    


main()               
