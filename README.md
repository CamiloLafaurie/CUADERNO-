# CUADERNO-
documentación y registro de ADSO

# descuento por noche 

dependiendo de la noches a hospedar se hara valido o no , el descuento 

    sub inicio
        precio<- 100
        escribir "Digite el numero de noches"
        leer noches

        total <- precio * noches

        si noches > 3 entonces 
            descuento <- total*.05
            
            escribir "Su pago total es: ", total - descuento 
        sino 
            
            escribir "su pago total sin descuento es: ", total
            
            
        FinSi
    end sub

# promedio de notas (designar aprovado o no aprovado)

en este programa en base a las notas de un estudiante se sacara su promedio y con ese promedio se decidira si es o no aprovado 

    sub inicio()
        definir alumno como caracter 
        definir examenparcial, examenfinal,promediopracticas como real
        definir final Como Real

        escribir "Digite el nombre del alumno" 
        leer alumno 

        Escribir "Las notas se calificaran de 1 - 10" 

        Escribir "Digite la nota del examen parcial"
        leer examenparcial
        Escribir "Digite la nota del examen final"
        leer examenfinal
        Escribir "Digite la nota del promedio de practicas"
        leer promediopracticas

        final <- (examenparcial+promediopracticas+(examenfinal*2))/3

        si final > 6 entonces 
            escribir "alumno aprobado: ", alumno 
            escribir "su promedio es: ", final 
        sino 
            
            escribir alumno, " alumno no aprobado"
            escribir "su promedio es: ", final 
	    FinSi
    end sub


# calculo de impuestos anuales

este programa nos calculara la cantidad de impuestos que debe pagar una empresa en base a los ingresos generados en el año 

    sub inicio()
        ingreso_anual = InputBox("Digite los ingresos anuales de la empresa: ")
        Total = 0
        impuesto = 0
        aumento = 0

        If ingreso_anual < 1000 And ingreso_anual > 0 Then
        MsgBox ("No debe pagar impuestos")
        Else
            If ingreso_anual >= 1001 And ingreso_anual <= 10000 Then
                aumento = (ingreso_anual * 0.05)
                MsgBox ("Total impuesto a pagar: ") & aumento
            Else
                If ingreso_anual >= 10001 And ingreso_anual <= 100000 Then
                aumento = (ingreso_anual * 0.1)
                MsgBox ("Total impuesto a pagar: ") & aumento
                
                Else
                    If ingreso_anual >= 100001 And ingreso_anual <= 1000000 Then
                        aumento = (ingreso_anual * 0.15)
                        MsgBox ("Total impuesto a pagar: ") & aumento
                    Else
                        If ingreso_anual >= 100000 And ingreso_anual <= 10000000 Then
                            aumento = (ingreso_anual * 0.2)
                            MsgBox ("Total impuesto a pagar: ") & aumento
                        Else
                            If ingreso_anual >= 10000001 Then
                                    aumento = (ingreso_anual * 0.25)
                                    MsgBox ("Total impuesto a pagar: ") & aumento
                                Else
                                    MsgBox "No se puede calcular"
                            End If
                            
                        End If
                    
                    End If
                    
                End If
                        
            End If

        End If
    end sub

# calculo de impuestos anuales (select case)

aqui ejecutamos la misma funcion que el anterior pero de una forma mas sencilla y practica

    sub inicio ()
        ingreso_anual = Int(InputBox("Digite los ingresos anuales de la empresa: "))
        aumento = 0
        
        Select Case ingreso_anual
        
        Case 0 To 1000
        MsgBox ("No debe pagar impuestos")
        
        Case 1001 To 10000
        aumento = (ingreso_anual * 0.05)
        MsgBox ("El total de impuestos a pagar es: ") & aumento
        
        Case 10001 To 100000
        aumento = (ingreso_anual * 0.1)
        MsgBox ("El total de impuesto a pagar es: ") & aumento
        
        Case 100001 To 1000000
        aumento = (ingreso_anual * 0.15)
        MsgBox ("El total de impuestos a pagar es: ") & aumento
        
        Case 1000000 To 10000001
        aumento = (ingreso_anual * 0.2)
        MsgBox ("El total de impuestos a pagar es: ") & aumento
        
        End Select
        
        If ingreso_anual >= 10000001 Then
                aumento = (ingreso_anual * 0.25)
                MsgBox ("Total impuesto a pagar: ") & aumento
                                
        End If
    end sub

# celdas (excel)

como asignar de unas celdas y almanecar los datos en otra

    Sub inicio()
        fila = datos.Cells(2, 7)
        datos.Cells(fila, 1) = formulario.Cells(8, 4)
        datos.Cells(fila, 2) = formulario.Cells(10, 4)
        datos.Cells(fila, 3) = formulario.Cells(12, 4)
        datos.Cells(fila, 4) = formulario.Cells(14, 4)
        MsgBox "Datos guardados"
        datos.Cells(2, 7) = fila + 1
    end sub

# registro de 15 nombres (celdas de excel)

aqui le pediremos al usuario que ingrese 15 nombres y nuestro programa se encarga de almacenar esos datos en las celdas asignadas

    sub inicio()
        For n = 2 To 16
        nombre = InputBox("Digite su nombre: " & n)
        datos.Cells(n, 1) = nombre

        Next n
    end sub

# calculo de abono de estudiantes 
en este programa podemos saber el total de una roleccion estudiantil, el promedio por estudiante, y quienes aportaron una suma (en este caso superior a 10k) en especifico dependiendo el valor que nosotros le asignemos 

    Sub inicio()
        
    abono = 0
    no_abono = 0
    cant = 0
    recaudo_total = 0
        
    For c = 1 To 2
        pregunta = InputBox("va a abonar para el evento? (si o no)")
        If pregunta = "si" Then
            abono = abono + 1
            dinero_r = Int(InputBox("Cuanto va a abonar?"))
            recaudo_total = recaudo_total + dinero_r
            If dinero_r >= 10000 Then
                cant = cant + 1
            End If
        Else
            no_abono = no_abono + 1
        End If
    Next c
        
    prom = recaudo_total / abono
    MsgBox "El total recaudado  es de $" & recaudo_total
    MsgBox "El promedio del recaudo total es de $" & prom
    MsgBox "Numero de estudiantes que si donaron " & "(" & abono & ")" & " Estudiantes"
    MsgBox "Numero de estudiantes que no donaron " & "(" & no_abono & ")" & " Estudiantes"
    MsgBox "Estudiantes que aportaron mas de $10.000:   " & "(" & cant & ")" & " Estudiantes"
            
    End Sub