# prueba-programacion
lista = []
def ingresar():
    while True:
        nombre = input("Ingrese nombre del usuario: ")
        line = False
        for linea in lista:
            if nombre in linea:
                line = True
        if line:
            print("Usuario ya existe. Intente otro.")
        elif not line:
            break
    while True:
        sexo = input("Ingrese sexo: ")
        if sexo == "M" or sexo == "F":
            break
        else:
            print("Debe ingresar M o F solamente. Intente denuevo.")
    while True:
        contra = input("Ingrese contraseña: ")
        if " " in contra or len(contra) < 8 or not contra.isalnum():
            print("Contraseña no valida. Intente otra.")
        else:
            print("Contraseña valida.")
            break
    lista.append(f"{nombre};{sexo};{contra}")
    print("Usuario ingresado con exito!!\n")

def buscar():
    name = input("Ingrese usuario a buscar: ")
    line = ""
    for linea in lista:
        if name in linea:
            line = linea
    if line != "":
        datos = line.split(";")
        print(f"El sexo del usuario es: {datos[1]} y la contraseña es: {datos[2]}\n")
    else:
        print("El usuario no se encuentra.\n")   

def eliminar():
    name = input("Ingrese usuario a buscar: ")
    line = False
    for linea in lista:
        if name in linea:
            line = True
            lista.remove(linea)
    if line:
        print("Usuario eliminado con éxito!\n")
    elif not line:
        print("No se pudo eliminar usuario!\n")


def opcion():
    while True:
        opcion = input("MENU PRINCIPAL\n1.-Ingresar usuario.\n2.- Buscar usuario\n3.- Eliminar usuario.\n4.- Salir.\nIngrese opción: ")
        print("")
        if opcion in "1234":
            if opcion == "1":
                ingresar()
            if opcion == "2":
                buscar()
            if opcion == "3":
                eliminar()
            if opcion == "4":
                print("Programa terminado...")
                break
        else:
            print("Debe ingresar una opción válida!!")

opcion()
        
    
