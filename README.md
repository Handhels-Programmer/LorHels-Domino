1. Sistema de Doble Acceso (Admin vs. Invitado)
El corazón de la app es la diferencia de permisos según el estado de conexión:

Modo Invitado (Público): Cualquier persona con el link puede entrar. Puede ver todas las mesas activas, los nombres de los jugadores, cuánto debe cada uno y cuántas partidas ha perdido. Sin embargo, no puede tocar nada; los botones de acción están ocultos y los nombres están bloqueados.

Modo Administrador: Al loguearte con tu correo y clave, la interfaz se "desbloquea". Aparecen los botones para registrar pérdidas, pagos, crear nuevas mesas, editar nombres de jugadores y cerrar partidas.

2. Gestión de Mesas y Jugadores
Creación Dinámica: Puedes crear una mesa nueva asignándole un nombre (ej. "Mesa VIP" o "Terraza"). Automáticamente se generan 4 jugadores.

Edición en Caliente: Como admin, puedes hacer clic sobre el nombre de cualquier jugador y cambiarlo (ej. de "Jugador 1" a "Andrés"). Al quitar el foco del texto, se guarda solo en la nube.

Eliminación: Un botón de papelera permite borrar mesas completas si hubo un error.

3. Lógica Contable de Juego
Cada jugador tiene dos contadores principales que se actualizan al instante:

Deuda ($): Se incrementa con el botón "PERDIÓ" (sumando el monto ingresado) y disminuye con el botón "PAGÓ".

Contador de Pérdidas: Cada vez que presionas "PERDIÓ", la app suma 1 al historial de derrotas de ese jugador en esa mesa. Esto permite saber quién es el "jugador del día" (o el que más está perdiendo).

4. Cierre de Partida e Historial
Validación de Cierre: La app no permite cerrar una mesa si algún jugador todavía tiene deuda pendiente. Esto asegura que nadie se vaya sin pagar.

Historial (Caja): Al cerrar una mesa, los datos se mueven a una colección de "History". Ahí se guarda quién fue el admin que cerró, cuánto dinero total se recaudó en esa mesa y qué jugadores participaron.

Estadísticas Globales: Tienes un panel superior que suma el total de mesas abiertas, el dinero pendiente por cobrar y el total acumulado en caja (historial).

5. Tecnología de Vanguardia
Firebase 11 (Firestore): Todo funciona con "WebSockets". Si tú cambias un precio desde tu PC, un invitado lo verá cambiar en su celular en menos de un segundo sin refrescar la página.

Seguridad por Reglas: Aunque un invitado sea un experto en computación, no podrá hackear el pago porque las reglas de tu base de datos exigen que solo un usuario autenticado pueda escribir datos.
