import random
def generar_mazos(n):
    mazo=[]
    for j in range(4):
        for i in range(1,14):
            mazo.append(i)
    random.shuffle(mazo)
    mazo=n*mazo
    return(mazo)
def jugar(m):
    valor=0
    while valor<21:
        carta=m.pop(0)
        valor=valor+carta
    return(valor)
def jugar_varios(m,j):
    puntaje=[]
    for i in range(j):
        valor=jugar(m)
        puntaje.append(valor)
    return(puntaje)
def ver_quien_gano(resultados):
    ganadores=[]
    i=0
    while i<len(resultados):
        if resultados[i]==21:
            winner=resultados[i]=1
            ganadores.append(winner)
        else:
            ganadores.append(0)
        i=i+1
    return(ganadores)
def experimentar(rep,n):
    nuevo_mazo=generar_mazos(n)
    nueva_lista=[]
    for i in range(rep):
        res=jugar_varios(nuevo_mazo,n)
        for j in range(len(res)):
            if res[i]==21:
    return(nueva_lista)
mazo2=generar_mazos(3)
valor=jugar(mazo2)
print(valor)
puntaje=jugar_varios(mazo2,3)
print(puntaje)
ganadores=ver_quien_gano(puntaje)
print(ganadores)
tabla=experimentar(5,4)
print(tabla)




    
    
