Comentario en el ejercicio: # TODO: Define la clase llamada VehiculoUber
Punto de análisis: ¿Cómo le indicamos a Python que estamos creando el "molde" y no una
variable o función común?
Checklist de éxito / Puntos a cuidar:
● Palabra reservada: Toda clase debe iniciar con la palabra class (en minúsculas).
● Convención del nombre: Los nombres de las clases usan CamelCase (inician con
Mayúscula y cada palabra nueva va en Mayúscula, sin espacios ni guiones bajos, ej.
VehiculoUber).
● Cierre de línea: No olvides poner los dos puntos : al final del nombre de la clase.
Escribe aquí la línea exacta de código con la que iniciarías tu clase:
class VehiculoUber:

2. Bloque: CONSTRUCTOR (__init__)

Comentario en el ejercicio: # TODO: Define el método constructor...
Punto de análisis: Es el método especial que "construye" al objeto en memoria. Si la sintaxis
de su nombre falla por un solo carácter, Python lo ignorará.
Checklist de éxito / Puntos a cuidar:
● Nombre exacto: Es __init__ con dos guiones bajos antes y dos guiones bajos después. No
es _init_, ni init.
● Sangría / Indentación: Como este método vive dentro de la clase, debe llevar una sangría
(4 espacios o un Tab) hacia la derecha.
● El parámetro obligatorio: El primer parámetro dentro de los paréntesis () SIEMPRE debe
ser self, seguido de los demás parámetros separados por comas.
Escribe aquí la línea del encabezado del constructor:

def __init__(self, marca, modelo, placa, conductor):

3. Bloque: ASIGNACIÓN DE ATRIBUTOS

Comentario en el ejercicio: # TODO: Asigna cada parámetro recibido a su atributo
correspondiente
Punto de análisis: Aquí es donde "guardamos" en la memoria permanente del objeto los datos
que llegaron por los paréntesis.
Checklist de éxito / Puntos a cuidar:
● Regla de self (Crear atributo): Para que el dato se quede guardado en el objeto debes
usar self.nombre_atributo = parametro.
● Distinción: Si solo escribes placas = placas, creas una variable local que se destruirá al
terminar el constructor. Con self.placa se vuelve una propiedad permanente del vehículo.
Escribe cómo asignarías el parámetro saldo_conductor a su atributo permanente:
self.marca = marca
self.modelo = modelo
self.placa = placa
self.conductor = conductor
self.en_viaje = False
self.saldo_conductor = 0.0

4. Bloque: MÉTODOS DE ACCIÓN (iniciar_viaje, completar_viaje, etc.)

Comentario en el ejercicio: # TODO: Crea el método 'iniciar_viaje' / 'completar_viaje'
Punto de análisis: Los métodos son las "acciones" que el objeto sabe realizar.
Checklist de éxito / Puntos a cuidar:
● Uso de def y sangría: Un método es una función dentro de una clase; usa def y mantén la
misma sangría que el constructor.
● Receptor self: ¿Recuerdas poner self como el primer parámetro de cada método que
crees? Ej. def iniciar_viaje(self, nombre_pasajero):.
● Modificar vs. Recibir:
○ costo_final o nombre_pasajero son datos temporales que entran por el paréntesis (sin
self).

○ self.saldo_conductor es el atributo permanente que vive en el objeto y se va a
modificar/acumular (+=).
Escribe la línea de código para actualizar el saldo acumulado en completar_viaje:
self.saldo_conductor += costo_final
def iniciar_viaje(self, nombre_pasajero):
self.en_viaje = True
print(f"Viaje iniciado para el pasajero: {nombre_pasajero}")

Las 3 Reglas de Oro de self (Para recordar durante el ejercicio)
1.
REGLA 1 (En la definición): Todo método dentro de una clase lleva self como primer
parámetro dentro de sus paréntesis: def metodo(self, ...):.
2. REGLA 2 (Adentro del método): Si quieres leer o modificar una propiedad del objeto
dentro de la clase, debes anteponer self. (ej. self.saldo_conductor += costo_final).
3. REGLA 3 (Al usar el objeto desde fuera): Cuando creas el objeto o llamas al método
desde fuera (uber_1.iniciar_viaje("Carlos")), NUNCA escribes la palabra self; Python la envía
por ti automáticamente.

# --- Prueba de métodos (opcional) ---
#auto_juan.actualizar_gps("Av. Vallarta 1500")
#auto_juan.aceptar_viaje()
#auto_alerta.bloquear_por_seguridad()
