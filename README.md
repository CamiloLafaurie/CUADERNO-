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
    End sub
# ejrcicio de recaudo con una suma mayor a x cantidad en este caso 3000000 usando el while y wend

    Sub sena()

    abono = 0
    no_abono = 0
    mas10k = 0
    Total = 0
    
    While Recaudo_final <= 3000000
        dinero = Int(InputBox("cantidad de dinero a abonar"))
        If dinero > 0 Then
            abono = abono + 1
            Recaudo_final = Recaudo_final + dinero
            If dinero >= 10000 Then
                mas10k = mas10k + 1
            End If
        Else
            no_abono = no_abono + 1
        End If
        
    Wend
    
    prom = Recaudo / abono
    MsgBox "total recaudado es de $" & Recaudo_final
    MsgBox "El promedio del recaudo es de $" & prom
    MsgBox "cantidad de estudiantes que abonaron " & "(" & abono & ")" & " Estudiantes"
    MsgBox "cantidad de estudiantes que no abonaron " & "(" & no_abono & ")" & " Estudiantes"
    MsgBox "estudiantes que abonaron mas de $10.000:   " & "(" & mas10k & ")" & " Estudiantes"
        
    End Sub
    ----------------------------------------------------------------------------
	    void main(){

	  Empresa empresa1 = Empresa(pais:'alemania',numero:1042242972,oficina:'porsche');
	  Empresa empresa2 = Empresa(pais:'reino unido',numero: 3105309540,oficina:'McLaren');
	  Empresa empresa3 = Empresa(pais:'italia',numero: 63329928,oficina:'lamborghini');

	  print("""
	  Usuarios de Empresas
	  1° Empresa:
	    Pais: ${empresa1.pais}.
	    Identificacion: ${empresa1.numero}.
	    Oficina: ${empresa1.oficina}.

	    Codigo: ${empresa1.generarCodigo()}.
	""");
	  empresa1.cantCaracteres();

	  print("""
	  2° Empresa:
	    Pais: ${empresa2.pais}.
	    Identificacion: ${empresa2.numero}.
	    Oficina: ${empresa2.oficina}.

	    Codigo: ${empresa2.generarCodigo()}.
	""");
	  empresa2.cantCaracteres();
	    print("""
	  3° Empresa:
	    Pais: ${empresa3.pais}.
	    Identificacion: ${empresa3.numero}.
	    Oficina: ${empresa3.oficina}.

	    Codigo: ${empresa3.generarCodigo()}.
	""");
	  empresa3.cantCaracteres();
	}
	class Empresa{
	  String? pais, oficina;
	  int? numero;

	  Empresa({this.pais, this.numero, this.oficina});

	  String? generarCodigo() => pais!.substring(0,3) + oficina!.substring(oficina!.length - 3, oficina!.length) + numero.toString().substring(0,3);

	  void cantCaracteres(){
	    int cantPais = pais!.length;
	    int cantOfic = oficina!.length;
	    String? convNum = numero.toString();
	    int cantNum = convNum.length;

	    print('pais:$cantPais,oficina:$cantOfic,numero:$convNum')
	}

	}

## json

~~~
import 'package:http/http.dart' as http;
import 'dart:convert' as convert;
void main() async {
  final url = Uri.https('jsonplaceholder.typicode.com', '/posts/4');
  final response = await http.get(url);
  if (response.statusCode == 200) {
    final json = convert.jsonDecode(response.body);
    print(json["id"]);
    print(json["title"]);
    print(json["body"]);
  } else {
    print('conteo de destruccion');
  }
}
~~~

##

~~~
import 'package:http/http.dart' as http;
import 'dart:convert' as convert;
void main() async {
  final url = Uri.https('reqres.in', 'api/users/1');
  final response = await http.get(url);
  if (response.statusCode == 200) {
    final json = convert.jsonDecode(response.body);
    print(json["data"]["email"]);
    print(json["data"]["first_name"]);
    print(json["support"]["url"]);
  } else {
    print('conteo de destruccion');
  }
}
~~~
~~~
void main(){
  Car car = Car(); 
  Accesorio parlante = Accesorio("Parlante");
  Accesorio aire = Accesorio("Aire"); 
  car.setAccesorio(parlante); 
  car.setAccesorio(aire);
  
  
  print(car.getAccesorio());
  
}
class Car{ 
  List <Accesorio> _accesorios = [];
  String? placa;
  
  void setAccesorio (Accesorio accesorio){
    _accesorios.add(accesorio);
  }
  
  List<Accesorio> getAccesorio(){
    return _accesorios;
  }
    
}
class Accesorio{ 
  String? nombre; 
  
  
  Accesorio(this.nombre);
   
  @override
  String toString() {
      return nombre!;
}
}

//main

~~~
	import 'package:flutter/material.dart';
	import 'package:project_one/widgets/Template.dart';
	import 'models/user.dart';
	import 'package:http/http.dart' as http;

	void main() => runApp(MyApp());

	class MyApp extends StatelessWidget {
	  @override
	  Widget build(BuildContext context) {
	    return MaterialApp(
	      title: 'first app',
	      home: Scaffold(
		appBar: AppBar(
		    title: Text('ventana principal'), backgroundColor: Colors.black),
		backgroundColor: Colors.white,
		body: FutureBuilder<User>(
		  future: getUser(),
		  builder: (context, snapshot) {
		    if (snapshot.connectionState == ConnectionState.done) {
		      User user = snapshot.data as User;
		      return Template(user: user);
		    }
		    return Center(child: CircularProgressIndicator());
		  },
		),
	      ),
	    );
	  }

	  Future<User> getUser() async {
	    final url = Uri.https('reqres.in', '/api/users/7');
	    final response = await http.get(url);
	    return User(response.body);
	  }
	}
~~~

//template

~~~
	import 'package:flutter/material.dart';
	import 'package:project_one/models/user.dart';

	class Template extends StatelessWidget {
	  const Template({
	    Key? key,
	    required this.user,
	  }) : super(key: key);

	  final User user;

	  @override
	  Widget build(BuildContext context) {
	    return Column(
	      children: [
		SizedBox(height: 15.0),
		Text(user.nombre!, style: TextStyle(fontSize: 20.0)),
		SizedBox(height: 15.0),
		Image(
		  image: NetworkImage(user.avatar!),
		),
		SizedBox(height: 15.0),
		Text(user.email!, style: TextStyle(fontSize: 20.0)),
		SizedBox(height: 15.0),
		Row(
		  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
		  children: [
		    Icon(Icons.person_add_alt_sharp,
			color: Colors.black,
			size: 40.0,
			semanticLabel: 'Text to announce in accessibility modes'),
		    Icon(Icons.favorite_rounded, color: Colors.red, size: 40.0),
		    Icon(Icons.insert_comment_rounded, color: Colors.black, size: 40.0),
		  ],
		)
	      ],
	    );
	  }
	}
~~~

//User
~~~
	import 'dart:convert' as convert;

	class User {
	  String? nombre;
	  String? avatar;
	  String? email;

	  User(String Json) {
	    final JsonResponse = convert.jsonDecode(Json);
	    nombre = JsonResponse["data"]["first_name"];
	    avatar = JsonResponse["data"]["avatar"];
	    email = JsonResponse["data"]["email"];
	  }
	}
~~~



