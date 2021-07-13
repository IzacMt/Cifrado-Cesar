# Cifrado-Cesar
Código para una decodificación por desplazamiento (cifrado Cesar) en python.

``` python

#Funcion para detectar idioma

def detectarIdioma(Texto,Mensaje,Desplazamiento):
    
    contador=0
    for palabra in Texto:
        if palabra == "the":
            contador+=1
        elif palabra == "be":
            contador+=1
        elif palabra == "to":
            contador+=1
        elif palabra == "of":
            contador +=1
        elif palabra == "and":
            contador +=1
        elif palabra == "in":
            contador +=1
        elif palabra == "that":
            contador +=1
        elif palabra == "have":
            contador +=1
        elif palabra == "I":
            contador +=1
        elif palabra == "it":
            contador +=1
        elif palabra == "a":
            contador +=1
    print(end="")
    if contador >=50:
        print("Su mensaje esta en ingles con una coincidencia de ", contador," palabras")
        print()
        print( end="" "Su mensaje decodificado es: ")
        print(Mensaje)
        print("El desplazamiento es: ",Desplazamiento)
    

#Creamos una funcion para decodificar 

def Decodificador(Texto):

    desplazamiento=1
    while desplazamiento<126:
        mensajeDeco = ""
        for caracter in Texto:
            codigo = caracter
            codigo = ord(codigo)+desplazamiento
            if codigo>125:
                restante=codigo-125
                codigo=32+restante-1
            codigo=chr(codigo)
            mensajeDeco=mensajeDeco+codigo
            
        detectarIdioma(mensajeDeco,mensajeDeco,desplazamiento)
        desplazamiento+=1
        
Mensaje = input('Ingrese el mensaje a decodificar: ')
print()
Decodificador(Mensaje)

```
