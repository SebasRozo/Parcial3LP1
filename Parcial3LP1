# PARCIAL 3 - LOGICA DE PROGRAMACION
# Integrante: Juan Sebastian Rozo Culma


# 1. DICCIONARIO Y TUPLAS: CATALOGO DE PRODUCTOS

productos = {
    1: ("Cafe", 3000, 20),
    2: ("Jugo natural", 5000, 15),
    3: ("Sandwich", 8000, 10),
    4: ("Empanada", 2500, 25),
    5: ("Hamburguesa", 12000, 8)
}


# 2. FUNCION PARA MOSTRAR LOS PRODUCTOS

def mostrar_productos(productos):

    print("\n========== CATALOGO DE PRODUCTOS ==========")
    print("Codigo   Producto          Precio     Existencias")

    for codigo, datos in productos.items():

        nombre = datos[0]
        precio = datos[1]
        existencias = datos[2]

        print(codigo, "     ", nombre, "       $", precio,
              "       ", existencias)


# 3. FUNCION PARA REGISTRAR PRODUCTOS

def registrar_producto(productos, pedido, codigo, cantidad):

    if codigo in productos:

        nombre = productos[codigo][0]
        precio = productos[codigo][1]
        existencias = productos[codigo][2]

        if cantidad > 0:

            if cantidad <= existencias:

                subtotal = precio * cantidad

                pedido.append((codigo, nombre, cantidad, subtotal))

                productos[codigo] = (
                    nombre,
                    precio,
                    existencias - cantidad
                )

                print("Producto agregado correctamente.")

            else:
                print("No hay suficientes unidades disponibles.")

        else:
            print("Cantidad no valida.")

    else:
        print("Producto no encontrado.")


# 4. FUNCION PARA CALCULAR EL TOTAL

def calcular_total(pedido):

    total = 0

    for producto in pedido:

        subtotal = producto[3]

        total = total + subtotal

    return total


# 5. FUNCION PARA MOSTRAR EL RESUMEN DEL PEDIDO

def mostrar_resumen(pedido):

    print("\n========== RESUMEN DEL PEDIDO ==========")

    print("Producto          Cantidad       Subtotal")

    for producto in pedido:

        nombre = producto[1]
        cantidad = producto[2]
        subtotal = producto[3]

        print(nombre, "          ", cantidad, "          $", subtotal)

    total = calcular_total(pedido)

    descuento = 0

    if total >= 50000:

        descuento = total * 0.10

    total_final = total - descuento

    print("-----------------------------------------")
    print("Total: $", total)
    print("Descuento: $", descuento)
    print("TOTAL A PAGAR: $", total_final)


# 6. PROGRAMA PRINCIPAL

def menu():

    pedido = []

    opcion = 0

    while opcion != 3:

        print("\n========== CAFETERIA ==========")
        print("1. Mostrar productos")
        print("2. Agregar producto al pedido")
        print("3. Finalizar pedido")

        try:
            opcion = int(input("Seleccione una opcion: "))

        except ValueError:
            print("Opcion no valida.")
            continue

        if opcion == 1:

            mostrar_productos(productos)

        elif opcion == 2:

            mostrar_productos(productos)

            try:
                codigo = int(input("\nIngrese el codigo del producto: "))
                cantidad = int(input("Ingrese la cantidad: "))

                registrar_producto(productos, pedido, codigo, cantidad)

            except ValueError:
                print("Ingrese valores numericos validos.")

        elif opcion == 3:

            if len(pedido) > 0:

                mostrar_resumen(pedido)

            else:
                print("No se registraron productos.")

            print("\nGracias por utilizar la cafeteria.")

        else:

            print("Opcion no valida.")


# EJECUTAR EL PROGRAMA

menu()
