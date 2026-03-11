1. Propósito de la aplicación

La app sirve para:

Administrar mesas de dominó

Registrar jugadores

Registrar pérdidas (deudas)

Registrar pagos

Ver historial de partidas

Controlar cuánto dinero se ha cobrado

Todo se guarda en Firebase Firestore, por lo que funciona en línea y en tiempo real.

2. Tecnologías utilizadas

La aplicación usa varias tecnologías modernas:

Frontend

HTML

Tailwind CSS → diseño visual

Lucide Icons → iconos

Google Fonts

Backend en la nube

Firebase

Authentication

Firestore Database

Analytics

Esto significa que no necesita servidor propio.

3. Interfaz principal de la app

La pantalla principal tiene:

Navbar

Contiene:

Logo del negocio

Estado de conexión (online / offline)

Botón de login de administrador

Botón de historial

Dashboard (solo para admin)

Muestra estadísticas:

💰 Caja del día

⚠️ Dinero pendiente (deudas)

🎲 Mesas activas

😅 El jugador que más ha perdido

Botón para crear mesas

El administrador puede crear nuevas mesas.

Ejemplo:

Mesa 1
Mesa VIP
Mesa 3

Cada mesa permite 4 jugadores.

4. Sistema de mesas de dominó

Cada mesa tiene:

Nombre de mesa

4 posiciones de jugador

Estado:

Libre

Ocupada

Ejemplo visual:

Mesa 2
Jugadores:
Juan
Pedro
Luis
Carlos

Deuda total: $300
5. Gestión de jugadores

El administrador puede:

Escribir el nombre del jugador

Registrar pérdidas

Registrar pagos

Cada jugador tiene:

nombre
deuda
pagado
partidas perdidas
6. Registrar pérdida (cuando un jugador pierde)

Se abre un modal llamado:

"Registrar Pérdida"

Ejemplo:

Jugador: Pedro
Monto: $100

La app hace:

deuda = deuda + monto
losses = losses + 1
7. Registrar pago

Si el jugador paga:

deuda = deuda - pago
pagado = pagado + pago

Ejemplo:

Pedro debe: $200
Pedro paga: $100
Nueva deuda: $100
8. Cerrar mesa

Cuando termina la partida:

El sistema verifica:

¿hay deudas pendientes?

Si hay deuda:

NO permite cerrar mesa

Muestra alerta:

Hay deudas pendientes.
Cobra antes de cerrar.

Si todo está pagado:

Guarda la partida en historial

Calcula el total cobrado

Libera la mesa

9. Historial de partidas

La app guarda:

Mesa
Fecha
Hora
Administrador
Jugadores
Total pagado

Ejemplo:

Mesa 1
10/03/2026
Jugadores: Juan, Pedro, Luis
Total: $800
10. Eliminación de mesas

El admin puede:

Eliminar mesa completamente

Esto no guarda historial.

11. Autenticación

Hay modo administrador.

Login:

Usuario
Contraseña

Los usuarios están guardados en:

Firestore → collection "users"

Cuando el login es correcto:

state.isAdmin = true

Esto desbloquea:

Crear mesas

Editar jugadores

Registrar deudas

Registrar pagos

Cerrar mesas

Ver estadísticas

12. Base de datos (Firebase)

La app usa Firestore con tres colecciones.

tables

Mesas activas

Ejemplo:

tables
   mesa1
      name
      status
      players[]
history

Historial de partidas

history
   partida1
      mesa
      jugadores
      totalPagado
      fecha
users

Usuarios administradores

users
   admin1
      username
      password
      label
13. Actualización en tiempo real

La app usa:

onSnapshot()

Esto significa que:

Si alguien cambia datos

Todos los dispositivos ven el cambio al instante

Ejemplo:

Un celular registra pago → la TV del bar lo ve inmediatamente.

14. Sistema de estado global

El sistema usa un objeto llamado:

state

Contiene:

user
isAdmin
tables
history
showHistory

Este objeto controla toda la app.

15. Seguridad

La app incluye:

Login de administrador

Verificación de pagos antes de cerrar mesa

Validación de montos

Confirmaciones antes de eliminar

16. Experiencia visual

El diseño es tipo:

Bar / Gaming / Dominó

Colores principales:

negro
ámbar
rojo
stone

Tiene:

animaciones

sombras

efectos hover

iconos

17. Lo interesante del sistema

Este código ya es un sistema comercial funcional para:

bares

colmados

clubes de dominó

billar

Permite llevar control de caja y deudas.

18. Posibles mejoras futuras

Este sistema podría mejorar con:

1️⃣ App para celulares

PWA o app móvil.

2️⃣ Ranking de jugadores

Quien gana más.

3️⃣ Estadísticas por jugador

Historial individual.

4️⃣ Control por camarero

Varios administradores.

5️⃣ Sistema de apuestas por partida
6️⃣ Pantalla pública

Mostrar resultados en TV.

19. Resumen

Esta app es un:

Sistema digital para administrar mesas de dominó en un bar

Permite:

crear mesas

registrar jugadores

registrar pérdidas

registrar pagos

cerrar partidas

guardar historial

controlar dinero

Todo en tiempo real usando Firebase.
