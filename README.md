print("hola")
# ============================================
# EJERCICIO: Identifica Clase, Métodos y Objetos
# Instrucción: Escribe comentarios al lado de cada parte
# indicando si es CLASE, MÉTODO u OBJETO.
# ============================================

class VehiculoUber:                          # ← ¿Qué es esto? ____CLASE___________
    
    def __init__(self, placas, conductor, modelo_auto, ubicacion_gps, calificacion):
        self.placas = placas
        self.conductor = conductor
        self.modelo_auto = modelo_auto
        self.ubicacion_gps = ubicacion_gps
        self.disponible = True
        self.calificacion = calificacion

    def actualizar_gps(self, nuevas_coordenadas):   # ← ¿Qué es esto? ____CLASE___________
        self.ubicacion_gps = nuevas_coordenadas
        print(f"{self.conductor} ahora está en: {self.ubicacion_gps}")

    def aceptar_viaje(self):                        # ← ¿Qué es esto? _______METODO________
        self.disponible = False
        print(f"{self.conductor} aceptó un viaje. Ya no está disponible.")

    def bloquear_por_seguridad(self):               # ← ¿Qué es esto? _________METODO______
        self.disponible = False
        print(f"⚠️ ALERTA: El vehículo de {self.conductor} ha sido bloqueado por seguridad.")




auto_juan = VehiculoUber(                           # ← ¿Qué es esto? ________METODO_______
    "JAL-9876", 
    "Juan Pérez", 
    "Chevrolet Aveo", 
    "Av. Vallarta y Américas", 
    4.9
)

auto_maria = VehiculoUber(                          # ← ¿Qué es esto? _________OBJETO______
    "JMX-4321", 
    "María Torres", 
    "Toyota Yaris", 
    "Centro de Tlaquepaque", 
    4.75
)

auto_alerta = VehiculoUber(                         # ← ¿Qué es esto? ________OBJETO_______
    "LMN-5555", 
    "Carlos R.", 
    "Nissan Sentra", 
    "Anillo Periférico Sur", 
    3.2
)


# --- Prueba de métodos (opcional) ---
#auto_juan.actualizar_gps("Av. Vallarta 1500")
#auto_juan.aceptar_viaje()
#auto_alerta.bloquear_por_seguridad()
