# CUADERNO-
documentación y registro de ADSO

# desuento por noche 
dependiendo de la noches a hospedar se hara valido o no , el descuento 

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

# calculo de impuestos anuales

este programa nos calculara la cantidad de impuestos que debe pagar una empresa en base a los ingresos generados en el año 

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

# calculo de impuestos anuales (select case)

aqui ejecutamos la misma funcion que el anterior pero de una forma mas sencilla y practica

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