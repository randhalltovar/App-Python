# App-Python
La arquitectura de la aplicación se distribuye en tres pantallas principales conectadas de manera secuencial a través de un controlador de vistas dinámico:

1. Panel de Bienvenida (Menú Principal)
Al iniciar el programa, se despliega una pantalla de bienvenida estilizada con un encabezado de gran formato. Este módulo actúa como distribuidor central y dispone de dos botones principales de navegación:

  * Abrir Calendario: Redirecciona de forma inmediata a la sección de agenda y control de fechas.
  * Abrir Notas: Da acceso al entorno del bloc de notas avanzado con almacenamiento multimedia.

2. Módulo de Calendario y Recordatorios 📅
Esta sección implementa un diseño de alto contraste optimizado específicamente para garantizar la legibilidad absoluta de los números, encabezados de días y barras de navegación.
  * Navegación y Estructura: El calendario muestra una cuadrícula visible que delimita con precisión cada día del mes. Los fines de semana se destacan automáticamente con un tono rojizo diferenciado para agilizar la lectura visual.
  * Creación de Recordatorios: Al hacer clic sobre cualquier celda numérica, el sistema actualiza el encabezado inferior con la fecha seleccionada y habilita un panel de edición. El usuario puede transcribir el texto deseado en la caja de entrada y presionar el botón Guardar. Los días con eventos asignados se renderizan con el fondo del color elegido para indicar una actividad programada.
    
  * Menú de Opciones Avanzadas: Situado en la esquina superior del panel de edición, este botón despliega un menú interactivo con las siguientes capacidades:
    - Configuración de Repeticiones: Permite automatizar recordatorios con frecuencia Anual (ideal para aniversarios o cumpleaños) o Mensual (útil para la gestión de pagos recurrentes).
    - Selector de Color: Abre una paleta de colores nativa del sistema para clasificar las notas por prioridades o categorías visuales.
      
  * Eliminación de Eventos: Si se selecciona un día que ya contiene información almacenada, la interfaz muestra de manera dinámica un botón para Eliminar, el cual remueve el registro del sistema y limpia la cuadrícula.

3. Entorno de Notas Avanzado 📝
Un bloc de notas diseñado bajo un enfoque de escritura fluida que combina herramientas multimedia con automatizaciones de resguardo crítico.

  * Organización y Búsqueda: El panel izquierdo centraliza la lista de documentos creados, mostrando el título y la última fecha de edición. Dispone de un botón para generar una + Nueva Nota de forma instantánea y una barra de búsqueda superior que filtra los elementos en tiempo real a medida que se escribe.

  * Sistema de Autoguardado Inteligente (Debounce): La aplicación carece deliberadamente de un botón manual de guardado para evitar pérdidas de información por descuidos. Integra un temporizador automático con un retraso (debounce) de 300 milisegundos; cada vez que el usuario detiene la escritura, el sistema procesa y resguarda los cambios en segundo plano.

💾 Persistencia de Datos y Respaldos
Tardis gestiona la persistencia de datos de manera local y descentralizada en el mismo directorio de ejecución de la aplicación, utilizando archivos de texto plano estructurados en formato JSON:

recordatorios.json: Almacena la relación de fechas, textos y códigos de color asociados a la agenda del calendario.
notes_db.json: Resguarda los identificadores únicos, títulos, cuerpos de texto formateados en HTML (incluyendo la codificación de imágenes incrustadas) y las marcas de tiempo de las notas.

