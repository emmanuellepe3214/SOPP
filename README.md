
# ============================================================
# ACTIVIDAD PRÁCTICA: La clase BandejaCorreo
# Emmanuel Lepe Robles ============================================================

# 1. DECLARACIÓN DE LA CLASE (El molde)
class BandejaCorreo:

    # 2. CONSTRUCTOR (Se ejecuta al crear la bandeja de entrada)
    def __init__(self, usuario, capacidad_maxima):
        # Guardamos los datos recibidos en la libreta del objeto ('self')
        self.usuario = usuario
        self.capacidad_maxima = capacidad_maxima
        
        # Atributos de estado inicial
        self.correos_recibidos = 0  # Inicia sin correos


    # 3. MÉTODOS DE ACCIÓN

    # ACCIÓN 1: Recibir un nuevo correo
    def recibir_correo(self, remitente):
        # Validamos si todavía hay espacio en la bandeja
        if self.correos_recibidos < self.capacidad_maxima:
            # Sumamos 1 al contador de correos recibidos
            self.correos_recibidos += 1
            
            # Mensaje de confirmación
            print(f"📧 {self.usuario} recibió un correo de {remitente}.")
        else:
            print(f"⚠️ ¡Bandeja llena! No se pudo recibir el correo de {remitente}.")


    # ACCIÓN 2: Consultar cuántos correos hay guardados
    def ver_estado(self):
        # Muestra en pantalla el usuario, los correos recibidos y su capacidad máxima
        print(f"📥 Usuario: {self.usuario}")
        print(f"📊 Correos en bandeja: {self.correos_recibidos} / {self.capacidad_maxima}")


# ============================================================
# 4. PRUEBA DEL CÓDIGO (Instanciación)
# ============================================================

# Creamos el objeto 'mi_bandeja' con el nombre "Ana" y capacidad máxima de 2 correos
mi_bandeja = BandejaCorreo("Ana", 2)

# Probamos recibir 3 correos seguidos para verificar el límite de capacidad
mi_bandeja.recibir_correo("carlos@gmail.com")
mi_bandeja.recibir_correo("ana@gmail.com")
mi_bandeja.recibir_correo("promociones@uber.com")  # Este debería rebotar por bandeja llena

# Consultamos el estado final
mi_bandeja.ver_estado()
