## Numeros aleatorios           
import random            

aleatorio = random.randint(0, 100)              
print(aleatorio)             

Generar 10 números aleatorios entre 0 y 100                                      
solo se agrega un range y queda                     

import random                

for i in range(10):               
    aleatorio = random.randint(0, 100)                 
    print(aleatorio)             

ahora agreguemos un flotante con 0.2               

import random                

for i in range(10):               
    aleatorio = random.randint(0, 100)               
    flotante = random.uniform(0.5,5.0)             
    print(f"{aleatorio} \t {flotante:0.2}")                

ahora agreguemos un flotante con 0.4                

import random            

for i in range(10):                   
    aleatorio = random.randint(0, 100)             
    flotante = random.uniform(0.5,5.0)               
    print(f"{aleatorio} \t {flotante:0.4}")               


import random import randint, uniform                

print("Enteros \t Flotantes ")             
print("_"*20)              
            
for i in range(10):                          
    aleatorio = random.randint(0, 100)                                               
    flotante = random.uniform(0.5,5.0)                              
    print(f"{aleatorio} \t {flotante:0.4}")                      

## Operadores Condicionales 

<img width="392" height="267" alt="image" src="https://github.com/user-attachments/assets/5c90766a-82b1-4e7e-8f71-2263a1f7e93a" />                                       

<img width="719" height="788" alt="image" src="https://github.com/user-attachments/assets/892869b3-1272-407e-8081-c3f1cf2d0184" />                     


## Bucles_2                        
Imprimir len patalla datos del 0 al 10                      

for i in range(10, -1, -1):                          
    print(i)                                           

# Tabla de multiplicar                  

num = int(input("Ingrese el número: "))                                      

for mult in range (1,11,1):             
    print(f"{num} x {mult} = {num*mult}")               

Con while                

contador = 0                 
while contador <= 10:                              
    print(f"{num} x {contador} = {num*contador} ")                  
    contador = contador + 1               

Menú de un restaurante             

print("1.) Platos fuertes\n2.) Bebidas\n3.) Postres\n4.)Salir")                  
Platos_fuertes = input("Ingrese su Plato fuerte: ")               
Bebidas = input("Ingrese su Bebida: ")             
Postres = input("Ingrese su Postre: ")        

opcion = int(input("Ingrese la opción deseada: "))                                     

while opcion != 4:                     
    if opcion == 1:           
        print(f"tus platos fuertes son {Platos_fuertes}")             
    elif opcion == 2:                 
        Bebidas = input("Ingrese su Bebida: ")               
    elif opcion == 3:            
        Postres = input("Ingrese su Postre: ")            
    elif opcion == 4:               
        print("Saliendo del menu... ")                 
    else:            
        print("Opcion no Válida")               

print("1.) Platos fuertes\n2.) Bebidas\n3.) Postres\n4.)Salir")                  
opcion = int(input("Ingrese la opción deseada: "))          

print("Pide lo que quieras\n1.) Platos fuertes\n2.) Bebidas\n3.) Postres\n4.)Salir")                 

opcion = int(input("Ingrese la opción deseada: "))                        

while True:                  
    if opcion == 1:             
        print("Platos fuertes: ")              
        platos_fuertes = input("Ingrese sus platos fuertes: ")            
        print("\n\n")                
        print(f"Usted eligió de plato: {platos_fuertes}")              
        print("\n\n")                                        
    elif opcion == 2:                                      
        print("Bebidas: ")              
        Bebidas = input("Ingrese su Bebida: ")           
        print("\n\n")             
        print(f"Usted eligió la bebida: {Bebidas}")           
        print("\n\n")           
    elif opcion == 3:                 
        print("Postres: ")              
        Postres = input("Ingrese su postre: ")                 
        print("\n\n")            
        print(f"Usted elegió el Postre")             
    elif opcion == 4:            
        print("Saliendo del menu... ")              
        break              
    else:           
        print("Opcion no Válida")              

print("1.) Platos fuertes\n2.) Bebidas\n3.) Postres\n4.)Salir")                          

opcion = int(input("Ingrese la opción deseada: "))                          

while opcion != 4:                   
    if opcion == 1:           
        print("Platos fuertes: ")                 
        print("1. Pizza\n2. Hamburguesa\n3. Lasagna")            
    elif opcion == 2:             
        print("Bebidas: ")             
        print("")            
          
def menu():            
    pass              
print("1.) Platos fuertes\n2.) Bebidas\n3.) Postres\n4.)Salir")              
              
opcion = int(input("Ingrese la opción deseada: "))           
return opcion               

## Ejercicio 1              
R = float(input("Ingrese el radio: "))                 
PI = 3.1416               
Area = PI * R * R               
# Formas distintas para poder imprimir estos ejercicios                 
print(f"Tu Área hallada es: {Area}")                  
print("El Área hallada es: ", Area)             
print(f"Tu Área hallada es {Area} m2")            

## Ejercicio 2         
num1 = float(input("Ingrese el primer número: "))                            
num2 = float(input("Ingrese el segundo número: "))         

if num1 > num2:                  
    print(f"{num1} es mayor")           
else:                                      

## Factorial                    
n = int(input("Ingrese el valor de n: "))                  
factorial = 1                      
contador = 1             
while contador <= n:               
      factorial = factorial * contador                
contador = contador + 1                
print(f"{n}! = {factorial}")             

# Ahora con for usando range con mi forma                   

n = int(input("Ingrese el valor de n: "))             
factorial = 1                  
contador = 1               
for i in range(n):                 
       factorial = factorial * contador                
       contador = contador + 1                  
print(f"{n}! = {factorial}")                   

# Ahora con for usando range con la forma del profe                           
n = int(input("Ingrese el valor de n: "))             
factorial = 1                  
for cont in range(1, n + 1):              
        factorial *= cont            
        print(f"{n}! = {factorial}")    
              
## Ejercicio primos                         
num = int(input("¿Su número a evaluar es?: "))          
cont = 0                   
for i in range(2, num, 1):            
    if (num % i) == 0:           
        cont += 1            
if cont == 0:             
    print(f"{num} es primo ")                
else:              
    print(f"{num} no es primo ")         

## Bucles y Cliclos     

<img width="637" height="534" alt="image" src="https://github.com/user-attachments/assets/2717b6f3-2e44-4e0a-acda-0f832020cf69" />                      

Condicionales             
print(10 > 5)           
print("Hola" != "Mundo")              
que imprimira?? imprime True                    

x = "hola"                                     
type(x)              
<class'str'>         
a = 3.14 <= 4.5              
print(3.14 <= 4.5)                
dira que es buleano como en todos                 

nombre = "Juan"                  
print(nombre == "Juan")              

envio = 0                 
compra = int(input("Ingrese el valor de la compra>> "))                        
if compra < 100000:                   
	envio = 9000                 
total = compra + envio                
print(f"El total de la compra es {total}")                    

## Ejercicio 4 Condicionales            
Edad = int(input("Introduzca su edad actual: "))                     
if Edad > 0:                    
    if Edad <= 6:               
        etapa = "Infancia"               
    elif Edad < 12:          
        etapa = "Niñez"                 
    elif Edad < 20:                             
        etapa = "Adolecencia"              
    elif Edad < 25:         
        etapa = "Juventud"                  
    elif Edad < 60:          
        etapa = "Vejez"            
    else:          
        etapa = "Vejez"                 
    print(f"Usted está en la etapa: {etapa} ")               
else:
     print("Edad invalida!")                     

## Ejercicio Calculadora                                                  

a = float(input("Ingrese número 1: "))                        
oper = input("Ingresa la operación deseada +,-,*,/, ^: ")                  
b = float(input("Ingrese número 2: "))                    
if oper == '+':                                
    resultado = a + b            
elif oper == '-':            
    resultado = a - b          
elif oper == '*':           
    resultado = a * b           
elif oper == '/':                                             
    resultado = a / b                
elif oper == '^':               
    resultado = a ** b             
else:            
    print("Sintax error")            
    resultado = "No ejecutado"              
print(f"{a} {oper} {b} = {resultado} ")              


a = float(input("Ingrese número 1: "))            
oper = input("Ingresa la operación deseada +,-,*,/, ^: ")              
b = float(input("Ingrese número 2: "))             

match oper:                                  

    case '+':                  
        resultado = a + b           
    case '-':           
        resultado = a - b           
    case '*':             
        resultado = a * b             
    case '/':            
        if b == 0:            
            print("Sintax error")    ## Averiguar el error          
    case '/':                
            resultado = a / b                  
    case '^':            
        resultado = a ** b                           
    case _:             
        print("Sintax error")             
        resultado = "No ejecutado"             
print(f"{a} {oper} {b} = {resultado} ")              



numero = 1000                      
while numero > 0:            
    if numero % 13 == 0:           
        print(numero)           
    numero -= 1            
                 
password = "h123-"                
contador = 0           

password = str("Ingrese su password: ")               
if  password == False:           
    print("Intente nuevamente: ")           
    contador = contador + 1           
elif password == True:               
    print("siga adelante"), contador      

## Funciones                                       
<img width="389" height="789" alt="image" src="https://github.com/user-attachments/assets/baf64393-54c3-437c-8aa9-ed920e4d553a" />                           

# Funciones en Python                      

Las funciones son bloques de código independientes que pueden recibir parámetros y realizar tareas específicas.                     
No están vinculadas a un objeto particular y se pueden llamar desde cualquier parte del código. Por ejemplo, la función `len()`                    
se utiliza para obtener la longitud de cualquier objeto iterable, como una lista o una cadena.      

# **Métodos de objetos                  

Los métodos son funciones específicas de un objeto en particular. Cada tipo de objeto en Python (como listas, cadenas, diccionarios, etc.)                        
tiene sus propios métodos que pueden utilizarse para realizar acciones específicas relacionadas con ese tipo de objeto. Los métodos están                 
vinculados al objeto y se llaman usando la notación de punto. Por ejemplo, el método `append()` se utiliza para agregar un elemento a una lista.                  
