# UTN-TUPaDProgramacion1

#Ejercicio 1: "Caja del kiosco"
nombre_cliente = input("Por favor, ingrese su nombre: ").strip()

while not nombre_cliente.isalpha():
    print("Error, sólo se permiten letras")
    nombre_cliente = input("Por favor, ingrese su nombre: ").strip()

cantidad_de_productos = input("Por favor, ingrese la cantidad de productos a comprar: ")

while not cantidad_de_productos.isdigit():
    print("Por favor, ingrese una cantidad válida: ")
    cantidad_de_productos = input("Por favor, ingrese la cantidad de productos a comprar: ")

cantidad_de_productos = int(cantidad_de_productos)
total_sin_descuentos = 0
total_con_descuentos = 0
ahorro_total = 0

while cantidad_de_productos <= 0:
    print("Por favor, ingrese una cantidad válida: ")
    cantidad_de_productos = input("Por favor, ingrese la cantidad de productos a comprar: ")
    cantidad_de_productos = int(cantidad_de_productos)

for i in range (cantidad_de_productos):
    precio_producto = input("Por favor, ingrese el precio del producto: ")
    descuento = 0
   
    while not precio_producto.isdigit():
            print("Error, ingrese un precio válido: ")
            precio_producto = input("Por favor, ingrese el precio del producto: ")

    precio_producto = int(precio_producto)

    tiene_descuento = input("Por favor, ingrese si el producto tiene descuento S/N: ").upper()

    while tiene_descuento != "S" and tiene_descuento != "N":
        print("Error, ingrese S o N")
        tiene_descuento = input("Por favor, ingrese si el producto tiene descuento S/N: ").upper()

    if tiene_descuento == "S":
        descuento = precio_producto * 0.1

    total_sin_descuentos += precio_producto
    precio_final = precio_producto - descuento
    total_con_descuentos += precio_final
    ahorro_total += descuento
    promedio_por_producto = total_con_descuentos / cantidad_de_productos
 
print(f"El total sin descuento es: {total_sin_descuentos}")
print(f"El total con descuentos es: {total_con_descuentos}")
print(f"El ahorro total es de: {ahorro_total}")
print(f"El promedio por producto es: {promedio_por_producto:.2f}")




#Ejercicio 2: "Acceso al campus y menú seguro"    
usuario_correcto = "alumno"
clave_correcta = "python123"
intentos = 0

while intentos < 3:
    nombre_usuario = input("Por favor, ingrese el nombre de usuario: ")
    clave_usuario = input("Por favor, ingrese la clave: ")

    if nombre_usuario != usuario_correcto or clave_usuario != clave_correcta:
        print("Error, nombre de usuario y/o clave incorrecta")
        intentos += 1

    else:
        break
    
if intentos == 3:
    print("Cuenta bloqueada")

else:
    while True:
        print("Menú:")
        print("1: Ver estado de inscripción")
        print("2: Cambiar clave")
        print("3: Mensaje motivacional")
        print("4: Salir")

        menu = input("Por favor, ingrese una opción del menu en números: ")

        if not menu.isdigit() or not (1 <= int(menu) <= 4):
            print("Opción inválida")
        else:
            match menu:
                case "1":
                    print("Inscripto")
                case "2":
                    nueva_clave = input("Por favor, ingrese una nueva clave de 6 caracteres: ")
                    while len(nueva_clave) < 6:
                        print("La clave debe tener 6 caracteres")
                        nueva_clave = input("Por favor, ingrese una nueva clave de 6 caracteres: ")
                    
                    confirmacion_nueva_clave = input("Por favor, reingrese la nueva clave: ")

                    if nueva_clave == confirmacion_nueva_clave:
                        print("Su clave se ha modificado con éxito")
                        clave_correcta = nueva_clave
                    
                    else:
                        print("Las claves no coinciden")
                case "3":
                    print("Con esfuerzo y constancia lograrás tus objetivos")
                case "4":
                    break




#Ejercicio 3: "Agenda de turnos con nombres (sin listas)"
lunes1 = ""
lunes2 = ""
lunes3 = ""
lunes4 = ""
martes1 = ""
martes2 = ""
martes3 = ""

nombre_operador = input("Por favor, ingrese su nombre: ")

while not nombre_operador.isalpha():
    print("Por favor, ingrese un nombre válido: ")
    nombre_operador = input("Por favor, ingrese su nombre: ")

while True:
    print("Menú: ")
    print("1: Reservar turno")
    print("2: Cancelar turno (por nombre)")
    print("3: Ver agenda del día")
    print("4: Ver resumen general")
    print("5: Cerrar sistema")

    menu = input("Por favor, ingrese una opción del menu en números: ")

    if not menu.isdigit() or not (1 <= int(menu) <= 5):
            print("Opción inválida")
            continue
    else:
        match menu:
            case "1":
                dia = input("Por favor seleccione un día: opción 1 para el lunes; opción 2 para el martes: ")
                while dia != "1" and dia != "2":
                    print("Por favor, seleccione una opción válida")
                    dia = input("Por favor seleccione un día: opción 1 para el lunes; opción 2 para el martes:")

                
                nombre_paciente = input("Por favor, ingrese el nombre del paciente: ")
                while not nombre_paciente.isalpha():
                        print("Por favor, ingrese un nombre válido")
                        nombre_paciente = input("Por favor, ingrese el nombre del paciente: ")
                
                if dia == "1" and lunes1 == "":
                    lunes1 = nombre_paciente
                    print("Turno asignado con éxito")
                elif dia == "1" and lunes2 == "":
                    lunes2 = nombre_paciente
                    print("Turno asignado con éxito")
                elif dia == "1" and lunes3 == "":
                    lunes3 = nombre_paciente
                    print("Turno asignado con éxito")
                elif dia == "1" and lunes4 == "":
                    lunes4 = nombre_paciente
                    print("Turno asignado con éxito")
                elif dia == "2" and martes1 == "":
                    martes1 = nombre_paciente
                    print("Turno asignado con éxito")
                elif dia == "2" and martes2 == "":
                    martes2 = nombre_paciente
                    print("Turno asignado con éxito")
                elif dia == "2" and martes3 == "":
                    martes3 = nombre_paciente
                    print("Turno asignado con éxito")        
                else:
                    print("Todos los turnos del día se encuentran ocupados")
                continue
            case "2":
                turno_a_cancelar = input("Por favor, ingrese el nombre del paciente del turno a cancelar: ")
                
                while not turno_a_cancelar.isalpha():
                    print("Por favor, ingrese un nombre válido: ")
                    turno_a_cancelar = input("Por favor, ingrese el nombre del paciente del turno a cancelar: ")
                
                if lunes1 == turno_a_cancelar:
                    lunes1 = ""
                    print("Turno cancelado con éxito")
                elif lunes2 == turno_a_cancelar:
                    lunes2 = ""
                    print("Turno cancelado con éxito")
                elif lunes3 == turno_a_cancelar:
                    lunes3 = ""
                    print("Turno cancelado con éxito")
                elif lunes4 == turno_a_cancelar:
                    lunes4 = ""
                    print("Turno cancelado con éxito")
                elif martes1 == turno_a_cancelar:
                    martes1 = ""
                    print("Turno cancelado con éxito")
                elif martes2 == turno_a_cancelar:
                    martes2 = ""
                    print("Turno cancelado con éxito")
                elif martes3 == turno_a_cancelar:
                    martes3 = ""
                    print("Turno cancelado con éxito")
                else:
                    print("el nombre del paciente no coincide con ningún turno asignado")
                continue

            case "3":
                turnos_del_dia = input("Por favor, ingrese 1 para ver los turnos del día lunes y 2 para ver los turnos del día martes: ").strip()

                while turnos_del_dia != "1" and turnos_del_dia != "2":
                    print("Por favor, ingrese una opción válida.")
                    turnos_del_dia = input("Por favor, ingrese 1 para ver los turnos del día lunes y 2 para ver los turnos del día martes: ")

                if turnos_del_dia == "1":
                    if lunes1 == "":
                        print(f"turno 1: libre")
                    else:
                        print(f"turno 1: {lunes1}")
                    if lunes2 == "":
                        print(f"turno 2: libre")
                    else:
                        print(f"turno 2: {lunes2}")
                    if lunes3 == "":
                        print(f"turno 3: libre")
                    else:
                        print(f"turno 3: {lunes3}")
                    if lunes4 == "":
                        print(f"turno 4: libre")
                    else:
                        print(f"turno 4: {lunes4}")
                if turnos_del_dia == "2":
                    if martes1 == "":
                        print(f"Turno 1: libre")
                    else:
                        print(f"Turno 1: {martes1}")
                    if martes2 == "":
                        print(f"Turno 2: libre")
                    else:
                        print(f"Turno 2: {martes2}")
                    if martes3 == "":
                        print(f"Turno 3: libre")
                    else:
                        print(f"Turno 3: {martes3}")
                continue   
            case "4":              
                turnos_libres_lunes = 0
                turnos_asignados_lunes = 0
                turnos_libres_martes = 0
                turnos_asignados_martes = 0    
                
                
                if lunes1 == "":
                    turnos_libres_lunes += 1
                else: 
                    turnos_asignados_lunes += 1
                if lunes2 == "":
                    turnos_libres_lunes += 1
                else: 
                    turnos_asignados_lunes += 1
                if lunes3 == "":
                    turnos_libres_lunes += 1
                else: 
                    turnos_asignados_lunes += 1
                if lunes4 == "":
                    turnos_libres_lunes += 1
                else: 
                    turnos_asignados_lunes += 1

                if martes1 == "":
                    turnos_libres_martes += 1
                else:
                    turnos_asignados_martes += 1
                if martes2 == "":
                    turnos_libres_martes += 1
                else:
                    turnos_asignados_martes += 1
                if martes3 == "":
                    turnos_libres_martes += 1
                else:
                    turnos_asignados_martes += 1

                print(f"Turnos asignados día lunes: {turnos_asignados_lunes}")
                print(f"Turnos libres día lunes: {turnos_libres_lunes}")
                print(f"Turnos asignados día martes: {turnos_asignados_martes}")
                print(f"Turnos libres día martes: {turnos_libres_martes}")

                if turnos_asignados_lunes < turnos_asignados_martes:
                    print("El día con más turnos asignados es el martes")
                elif turnos_asignados_lunes > turnos_asignados_martes:
                    print("El día con más turnos asignados es el lunes")
                else:
                    print("El lunes y el martes cuentan con la misma cantidad de turnos asignados")
                continue
            case "5":
                break



#Ejercicio 4: "Escape room: la bóveda"
energia = 100
tiempo = 12
cerraduras_abiertas = 0
alarma = False
codigo_parcial = ""
anti_spam = 0

nombre_agente = input("Por favor, ingrese su nombre: ").upper().strip()

while not nombre_agente.isalpha():
    print("Por favor, ingrese un nombre válido")
    nombre_agente = input("Por favor, ingrese su nombre: ").upper().strip()

while energia > 0 and tiempo > 0 and cerraduras_abiertas < 3:
    print(f"Energía= {energia}")
    print(f"Tiempo= {tiempo}")
    print(f"Cerraduras abiertas= {cerraduras_abiertas}")
    print(f"Alarma= {alarma}")
    print(f"Código parcial= {codigo_parcial}")
    print(f"Anti-spam= {anti_spam}")

    print("Menú:")
    print("1- Forzar cerradura")
    print("2- Hackear panel")
    print("3- Descansar")
    eleccion = (input("Por favor, ingrese una opción del menú: "))

    while not eleccion.isdigit() or (eleccion != "1" and eleccion != "2" and eleccion != "3"):
        print("Por favor, seleccione una opción válida")
        eleccion = (input("Por favor, ingrese una opción del menú: "))

    if eleccion == "1":
        energia -= 20
        tiempo -= 2
        anti_spam += 1

        if anti_spam == 3:
            alarma = True

        if alarma == False:
            cerraduras_abiertas += 1

        if energia < 40:
            riesgo_alarma = input("Por favor, ingrese un número del 1 al 3: ")
            while not riesgo_alarma.isdigit() or (riesgo_alarma != "1" and riesgo_alarma != "2" and riesgo_alarma != "3"):
                print("Por favor, seleccione una opción válida")
                riesgo_alarma = (input("Por favor, ingrese un número del 1 al 3: "))
            if riesgo_alarma == "3":
                alarma = True

    if eleccion == "2":
        energia -= 10
        tiempo -= 3
        anti_spam = 0

        for i in range (4):
            codigo_parcial += "A"

        if len(codigo_parcial) >= 8 and cerraduras_abiertas < 3:
            cerraduras_abiertas += 1

    if eleccion == "3":
        anti_spam = 0
        tiempo -= 1
        if energia <= 85:
            energia += 15
        if alarma == True:
            energia -= 10

    if alarma == True and tiempo <= 3:
        print("DERROTA (bloqueo)")
        break
        
    if cerraduras_abiertas == 3:
        print("VICTORIA")
        break
        
    if energia <= 0 or tiempo <= 0:
        print("DERROTA")
        break



#Ejercicio 5: "Escape room: La arena del gladiador"
vida_gladiador = 100
vida_enemigo = 100
pociones_vida = 3
danio_base_gladiador = 15 
danio_base_enemigo = 12 
turno_gladiador = True 

nombre_gladiador = input("Ingrese el nombre del gladiador: ").strip().upper()

while not nombre_gladiador.isalpha():
    print("Por favor, ingrese un nombre válido: ")
    nombre_gladiador=input("Ingrese el nombre del gladiador: ").strip().upper()

while vida_enemigo > 0 and vida_gladiador > 0:
    if turno_gladiador:
        print("Truno Gladiador")
        print(f"El Gladiaro {nombre_gladiador} tiene {vida_gladiador} puntos de vida")
        print(f"El enemigo tiene {vida_enemigo} puntos de vida")
        print(f"Te quedan {pociones_vida} pociones de vida")

        while True:
            print("1) Ataque pesado")
            print("2) Ráfaga veloz")
            print("3) Curar")
                
            opcion = input("Elegi una opcion de accion: ")
            
            match opcion:
                    
                case "1":
                    danio = danio_base_gladiador
                    if vida_enemigo < 20:
                        danio = danio*1.5
                    vida_enemigo = vida_enemigo-danio 
                    print(f"¡Atacaste al enemigo por {danio} puntos de daño!")
                    break
                    
                case "2":
                    for i in range(3):
                        vida_enemigo = vida_enemigo-1
                        print("Golpe conectado por 1 de daño")
                    break
                    
                case "3":
                    if pociones_vida > 0:
                        vida_gladiador = vida_gladiador+30
                        pociones_vida = pociones_vida-1
                    else:
                        print("¡No quedan pociones!")
                        print("Perdiste el turno")
                    break
                    
                case _:
                    print("El valor ingresado es invalido, intente de nuevo")

        turno_gladiador = False

    else:
        vida_gladiador = vida_gladiador-danio_base_enemigo
        print("¡El enemigo te atacó por 12 puntos de daño!") 
        turno_gladiador=True

if vida_gladiador > 0:
        print(f"¡VICTORIA! {nombre_gladiador} ha ganado la batalla.")
    
else:
    print("DERROTA. Has caído en combate.")
                    




    

                
                    
                    
