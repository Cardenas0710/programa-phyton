sesiones = []

def clasificar_compromiso(duracion, clics):

    if duracion > 180 and clics > 8:
        return "Alto"

    elif duracion < 60 or clics < 3:
        return "Bajo"

    else:
        return "Medio"

cantidad = int(input("¿Cuántas sesiones desea ingresar?: "))

while cantidad < 5:

    print("Error: Debe ingresar mínimo 5 sesiones.")

    cantidad = int(input("Ingrese nuevamente la cantidad: "))

for i in range(cantidad):

    print("\nSesión", i + 1)

    id_cliente = input("Ingrese el ID del cliente: ")

    duracion = int(input("Ingrese la duración en segundos: "))

    clics = int(input("Ingrese la cantidad de clics: "))

    sesiones.append([id_cliente, duracion, clics])

print("\nMATRIZ DE DATOS INGRESADOS")

for fila in sesiones:
    print(fila)

print("\nREPORTE FINAL")

for sesion in sesiones:

    id_cliente = sesion[0]
    duracion = sesion[1]
    clics = sesion[2]

    clasificacion = clasificar_compromiso(duracion, clics)

    print("Cliente:", id_cliente,
          "| Clasificación:", clasificacion)
