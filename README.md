# 5to-Rojo-Francisco-Velasquez-
Pensamiento Computacional 
Clase 1 Modificación de Readme



Clase 2: Actividad 
Patrón : por cada arepa adicional, el precio total decrece en 2 Bs. (pasa de aumentar 8, luego 6, luego 4, luego 2 Bs).
Fórmula matemática Como el aumento disminuye de manera constante, la relación es de tipo cuadrática: (n es la cantidad de arepas y P el precio total). P(n) = n(11 - n)
Fórmula aplicada P(10) = 1(10) - 10^2 = 110 - 100 = 10 \BsSiguiendo este patrón matemático el precio marginal seguirá bajando y se hará negativo en cierto punto lo demuestra un límite práctico del modelo.
Fórmula generalizada Si a = precio, diferencia= (a - 2) y disminuye de 2 en 2. P(n) = (a + 1)n - n^2
Reflexión: ¿Por qué el precio no aumenta siempre lo mismo? Porque se está aplicando un descuento por volumen. Mientras más arepas compra el cliente, menor es el precio por unidad adicional para incentivar ventas al mayor.  ¿Qué pasaría si el patrón cambiara? Si el aumento fuera constante (ej. +10 Bs por arepa), el modelo sería lineal (\bm{P = 10n}). Si el patrón no sigue una regla lógica, la automatización del software no podría predecir los precios correctamente y habría pérdidas para el negocio o cobros incorrectos al cliente.



clase 3: actividad de distancias representamos un mapa con circulos y lineas usando papel, marcadores y regla. propusimos rutas sumando distancias entre las ciudades propuestas, aplicando nuestros conocimientos para emcontrar la ruta mas corta, Ademas armamos un circuito con 6 LED en paralelo y 2 Led de distintos colores Actividades adjuntas:
https://www.tinkercad.com/things/4DJ0ZFa71jE/editel?returnTo=%2Fdashboard&sharecode=Oh26H2tdtvVJIqiMgYCDjYdj-9GXIkGFBVOfgNrjOyo

CLASE 5:
Actividad 23/10 – Pensamiento Computacional
Ejercicio 1: Centro de atención

1. Descomposición en subproblemas
- Llegada:el estudiante llega al centro y toma su turno.
- Registro: se anotan sus datos y el tipo de trámite que va a hacer.
- Prioridades: se revisa si su caso es prioritario o normal.
- Atención: la ventanilla llama al siguiente estudiante y lo atiende.
- Cierre: se marca el trámite como terminado y se registra la hora de salida.

2. Datos de cada estudiante
Para cada estudiante se necesita:
- Cédula o carnet, para identificarlo.
- Nombre.
- Hora de llegada, para respetar el orden.
- Tipo de trámite: entrega de documentos, solicitud de constancia o consulta general.
- Prioridad (sí o no) y el motivo.
- Tiempo estimado del trámite.
- Estado: en espera, atendiendo o finalizado.
  
3. Algoritmo en pseudocódigo

Inicio
  Crear ColaPrioritaria y ColaNormal
  contadorPrioritarios = 0
  Mientras el centro esté abierto Hacer
    Si llega un estudiante Entonces
      Registrar cédula, nombre, hora de llegada y tipo de trámite
      Si es prioritario Entonces
        Agregar a ColaPrioritaria
      SiNo
        Agregar a ColaNormal
      FinSi
    FinSi
    Si la ventanilla está libre Entonces
      Si ColaPrioritaria no está vacía Y contadorPrioritarios < 3 Entonces
        Atender al primero de ColaPrioritaria
        contadorPrioritarios = contadorPrioritarios + 1
      SiNo
        Si ColaNormal no está vacía Entonces
          Atender al primero de ColaNormal
          contadorPrioritarios = 0
        SiNo
          Si ColaPrioritaria no está vacía Entonces
            Atender al primero de ColaPrioritaria
          FinSi
        FinSi
      FinSi
      Registrar hora de fin y cambiar estado a "Finalizado"
    FinSi
  FinMientras
Fin

4. Criterio de prioridad

Consideré prioritarias a las personas con discapacidad, las embarazadas y los casos de emergencia, porque esperar mucho tiempo las afecta más que al resto. Dentro de cada grupo se respeta el orden de llegada para que sea justo. También agregué una regla: después de atender a 3 prioritarios seguidos se atiende a 1 de la cola normal. Así la fila normal no se queda esperando sin avanzar, y esto ayuda a reducir el tiempo promedio de espera.

Ejercicio 2: Ruta del autobús escolar
1. Representación de paradas y distancias

Como el enunciado no daba números, propuse distancias aproximadas en kilómetros entre la escuela (S) y las 6 paradas (A, B, C, D, E y F). Las organicé en una tabla donde cada casilla indica la distancia entre dos puntos:

| | S | A | B | C | D | E | F |
|---|---|---|---|---|---|---|---|
| S | – | 2 | 5 | 7 | 6 | 4 | 3 |
| A | 2 | – | 3 | 6 | 7 | 5 | 2 |
| B | 5 | 3 | – | 2 | 4 | 6 | 5 |
| C | 7 | 6 | 2 | – | 3 | 5 | 6 |
| D | 6 | 7 | 4 | 3 | – | 2 | 4 |
| E | 4 | 5 | 6 | 5 | 2 | – | 2 |
| F | 3 | 2 | 5 | 6 | 4 | 2 | – |

2. Algoritmo para construir la ruta:
  

1. Empezar en la escuela (S).
2. Buscar en la tabla la parada no visitada más cercana al punto actual.
3. Ir a esa parada, recoger a los estudiantes y marcarla como visitada.
4. Repetir los pasos 2 y 3 hasta visitar las 6 paradas.
5. Regresar a la escuela.

3. Aplicación del algoritmo

- Desde S, la más cercana es A (2 km).
- Desde A, la más cercana es F (2 km).
- Desde F, la más cercana es E (2 km).
- Desde E, la más cercana es D (2 km).
- Desde D, la más cercana es C (3 km).
- Desde C, solo queda B (2 km).
- Desde B, regreso a S (5 km).

Ruta propuestas: S → A → F → E → D → C → B → S
Distancia total 2 + 2 + 2 + 2 + 3 + 2 + 5 = **18 km**

4. Comparación con otra ruta

Ruta alternativa:** S → A → B → C → D → E → F → S
Distancia total: 2 + 3 + 2 + 3 + 2 + 2 + 3 = **17 km**

Mi criterio fue la menor distancia, y con ese criterio la ruta alternativa es mejor por 1 km. Ambas rutas tienen las mismas 6 paradas, así que la diferencia está solo en la distancia. Con esto me di cuenta de que el vecino más cercano no siempre encuentra la mejor ruta, porque en cada paso elige lo más cercano sin mirar el recorrido completo. Al final la última parada (B) quedó lejos de la escuela y eso aumentó el total. Aun así, el método da una ruta razonablemente corta de forma rápida, y por eso es útil cuando hay muchas paradas.

Ejercicio 3: Promedio de notas

Pseudocódigo original:
Inicio
  Leer nota1, nota2, nota3
  promedio = nota1 + nota2 + nota3
  Si promedio >= 60 Entonces
    Escribir "Aprueba"
  SiNo
    Escribir "No aprueba"
  FinSi
Fin

1. Errores y limitaciones

- No calcula el promedio: solo suma las notas y no divide entre 3. Por ejemplo, con notas de 30, 20 y 25 la suma da 75, que es mayor que 60, y el programa dice "Aprueba" aunque el promedio real es 25.
- No valida las notas: acepta valores fuera del rango, como -10 o 150.
- No muestra el promedio: solo dice si aprueba o no, y el estudiante no sabe cuál fue su nota final.
- Solo funciona con 3 notas: si hay más evaluaciones, hay que reescribir el código.

2. Pseudocódigo corregido
Inicio
  Leer nota1, nota2, nota3
  promedio = (nota1 + nota2 + nota3) / 3
  Si promedio >= 60 Entonces
    Escribir "Aprueba"
  SiNo
    Escribir "No aprueba"
  FinSi
Fin

Agregué la división entre 3 y puse la suma entre paréntesis. Sin los paréntesis, la computadora primero divide y después suma, así que solo dividiría la última nota.

3. Validación de notas entre 0 y 100
Inicio
  Repetir
    Leer nota1
  Hasta Que nota1 >= 0 Y nota1 <= 100
  Repetir
    Leer nota2
  Hasta Que nota2 >= 0 Y nota2 <= 100
  Repetir
    Leer nota3
  Hasta Que nota3 >= 0 Y nota3 <= 100
  promedio = (nota1 + nota2 + nota3) / 3
  Si promedio >= 60 Entonces
    Escribir "Aprueba"
  SiNo
    Escribir "No aprueba"
  FinSi
Fin

Usé un ciclo "Repetir... Hasta Que" para que el programa pida la nota otra vez mientras esté fuera del rango. Así se evita que una nota equivocada dañe el resultado.

4. Mejora adicional
Inicio
  suma = 0
  Para i = 1 Hasta 4 Hacer
    Repetir
      Escribir "Ingrese la nota ", i
      Leer nota
      Si nota < 0 O nota > 100 Entonces
        Escribir "Nota inválida, debe estar entre 0 y 100"
      FinSi
    Hasta Que nota >= 0 Y nota <= 100
    suma = suma + nota
  FinPara
  promedio = suma / 4
  Escribir "Promedio: ", promedio
  Si promedio >= 60 Entonces
    Escribir "Aprueba"
  SiNo
    Si promedio >= 50 Entonces
      Escribir "Debe ir a recuperación"
    SiNo
      Escribir "No aprueba"
    FinSi
  FinSi
Fin
