=================
Detalles técnicos
=================

Administración del CPU
======================

.. image:: imagenes/cpu.jpg
    :scale: 40 %
    :align: center
    

* **Kernel:** El núcleo o kernel proporciona el acceso a los distintos elementos del hardware del dispositivo. Ofrece distintos servicios a las superiores como son los controladores odrivers para el hardware, la gestión de procesos, el sistema de archivos y el acceso a la gestión de la memoria.

* **Middleware:** El middleware es el conjunto de módulos que hacen posible la propia existencia de aplicaciones para móviles. Es totalmente transparente para el usuario y ofrece servicios claves como el motor de mensajera y comunicaciones, códecs multimedia,intérpretes de páginas web, gestión del dispositivo y seguridad. 

* **Aplicaciones:** El entorno de ejecución de aplicaciones consiste en un gestor de aplicaciones y un conjunto de interfaces programables abiertas y programables por parte de los desarrolladores para facilitar la creación de software.

* **Interfaz de usuario:** Las interfaces de usuario facilitan la interacción con el usuario y el diseño de la presentación visual de la aplicación. Los servicios que incluye son el de componentes gráficos (botones, pantallas, listas, etc.) y el del marco de interacción.

Aparte de estas capas también existe una familia de aplicaciones nativas del teléfono que suelen incluir los menús.


Gestión de la memoria principal
===============================

.. image:: imagenes/mem.jpg
    :scale: 20 %
    :align: center


Al igual que Java y .NET, Android utiliza el entorno de ejecución y la máquina virtual para gestionar la memoria de la aplicación. A diferencia de cualquiera de estos dos marcos, el entorno de ejecución de Android también maneja los tiempos de vida del proceso.

Android asegura la respuesta de la aplicación, deteniendo y matando a los procesos que obstaculizan la fluidez y libera recursos para las aplicaciones de mayor prioridad. Cada aplicación Android se ejecuta en un proceso independiente dentro de su propia instancia de Dalvik, renunciando a toda responsabilidad de la memoria y la gestión de procesos.

Dalvik y el entorno de ejecución de Android se posicionan en la parte superior de un núcleo de Linux que se encarga de la interacción de bajo nivel del hardware, incluyendo los drivers y la gestión de memoria, mientras que el conjunto de API proporciona acceso a todos los servicios de bajo nivel, características y hardware.


Sistema de archivos
===================

.. image:: imagenes/ext4.jpg
    :align: center


Con la aparición en el mercado del móvil Nexus S Android comenzó a utilizar el sistema de archivos llamado Ext4.

El Ext4 es el sistema de archivos que implementan la mayoría de distribuciones de Linux, y sobre todo es bastante estable y confiable como la mayoría de los sistemas basados en Linux, con el mínimo riesgo de pérdida de información. Este surgió como una mejora compatible de ext3. Las principales mejoras son:

* Soporte de volúmenes de hasta 1024 PiB.
* Soporte añadido de extent.
* Menor uso del CPU.
* Mejoras en la velocidad de lectura y escritura.

La mayoría de dispositivos con Android utilizan un sistema de ficheros llamado YAFFS, un desarrollo ligero optimizado para almacenamiento Flash y que ya se usaba en otros dispositivos móviles, pero surge un problema, y es que el sistema YAFFS es un sistema orientado a sistemas con un único hilo de ejecución, lo que supondría la aparición de cuellos de botella en sistemas dual-core.

Los programadores tendrán que tener en cuenta el comportamiento de Ext4 a la hora de realizar el buffering, y deben asegurarse de que los datos llegan de forma real al almacenamiento persistente para que no haya errores de sincronización.


Sistemas de protección
======================

.. image:: imagenes/proteccion.jpg
    :align: center
    
    
Google ha revelado que cuenta con un sistema de protección denominado “Bouncer”, que detecta aplicaciones con código malicioso en la misma plataforma una vez que son subidas.

Bouncer provee un escaneo automático del Android Market buscando software potencialmente malicioso sin alterar la experiencia del usuario en el Android Market o hacer que los desarrolladores pasen por un proceso de aprobación de aplicaciones.

El software básicamente funciona escaneando cualquier tipo de comportamiento sospechoso de una aplicación y alertando en caso de encontrar cualquier indicio de malware o spyware.

De esta forma se consigue un banco de aplicaciones más fiable donde el usuario puede descargar con cierta tranquilidad las aplicaciones de su gusto.


Sistema de comunicaciones
=========================

La API de Android aporta mecanismos para realizar comunicación entre dispositivos o a través de la red. Estos sistemas estarán disponibles dependiendo del hardware del teléfono.

Existen distintos tipos de comunicación:

* Red (conexión directa, wifi...)
* Telefonía
* Bluetooth

Wifi
----

.. image:: imagenes/wifi.jpeg
    :align: center
    

El paquete android.net.wifi provee los mecanismos por los cuales una aplicación Android puede acceder a la pila Wifi del sistema. Las clases contenidas en android.net.wifi informan desde los puntos de acceso detectados hasta el estado de la propia conexión. El paquete también proporciona los métodos necesarios para escanear el entorno, iniciar y detener conexiones, configurar nuevas conexiones, etc


Telefonía
---------

.. image:: imagenes/telefonia.jpg
    :scale: 50 %
    :align: center
    
    
La API android.telephony proporciona recursos para acceder a la información básica del teléfono, tal como el
tipo de red, estado de la conexión, gestión de números de teléfono, etc.

Las principales clases implicadas son:

* **NeighboringCellInfo:** proporciona información de la celda más cercana.
* **PhoneNumberUtils:** clase de ayuda para la gestión de Strings telefónicos.
* **PhoneStateListener:** clase que gestiona los cambios de estado del teléfono.
* **SMSManager:** operaciones de SMS.
* **SMSMessage:** mensaje SMS.
* **TelephonyManager:** Acceso a los servicios de telefonía del dispositivo.


Bluetooth
---------

.. image:: imagenes/bluetooth.png
    :align: center
    

La API de Android soporta Bluetooth desde la versión 2.0. Con Bluetooth se permite:

* Buscar otros dispositivos bluetooth.
* Consultar si está emparejado con un dispositivo bluetooth concreto.
* Establecer canales RFCOMM.
* Conectar con otros dispositivos a través del servicio de descubrimiento de dispositivos.
* Realizar transferencia de datos entre otros dispositivos de forma bidireccional.
* Manejar múltiples conexiones


Programas de sistema
====================

.. image:: imagenes/programas.jpeg
    :align: center


Ya existen 700.000 aplicaciones disponibles para descargar en dispositivos Android, según ha confirmado Google.

El número de aplicaciones disponibles en una plataforma es uno de los factores a tener en cuenta para determinar su importancia.


Administración de tareas
========================

.. image:: imagenes/administrador.jpg
    :scale: 40 %
    :align: center


Este tipo de aplicaciones nos muestran el uso de la memoria y el CPU que tiene nuestra máquina, y lo que és más importante, nos permiten cerrar tareas que se cargan (o bloquean) innecesariamente la memoria y disminuyen el rendimiento del sistema, evitando así una caida generalizada del mismo. Es una aplicación de vital importancia en cualquier SO, por lo tanto viene de serie en todos.

Android no ofrece esta característica. Esta es una de las varias incomprensibles carencias de este SO. Pero, si podemos instalarle un buen administrador de tareas desde el Market. Como por ejemplo:

* Automatic Task Killer
* Task Manager
* Advanced Task Killer
* TasKiller
* Advanced Task Manager 


Administración de usuarios
==========================

Si hay algo que muchos echan de menos en Android, es la posibilidad de definir diferentes cuentas de usuario, tal y como ocurre en los sistemas operativos tradicionales. Quizás para los smartphones no sea un gran añadido, pero dado que las tablets con Android se van haciendo su sitio en el mercado, y que un gran porcentaje de usuarios las utilizan en familia, esta funcionalidad sería muy bien recibida.

.. image:: imagenes/switchme.jpg
    :scale: 80 %
    :align: center


Para crear diferentes cuentas de usuario en Android se puede utilizar la aplicación SwitchMe, que crea diferentes perfiles según querramos (incluyendo aplicaciones, ajustes y datos) que se almacenan en el terminal y entre los cuales se pueden cambiar fácilmente. De este modo:

* Se puede crear una cuenta privada protegida con contraseña, muy útil si compartes tu dispositivo con alguien más.
* Podes utilizar esta aplicación para crear perfiles públicos con las apps que tu quieras.
* Se puede ahorrar energía corriendo un perfil con poco consumo de recursos.
* O simplemente crear un perfil para testear aplicaciones.


El sistema de E/S
=================

.. image:: imagenes/bluectrl.jpg
    :scale: 60 %
    :align: center


Debido a la flexibilidad de Android podemos conectarle dispositivos de entrada o salida muy facilmente y por diversos medios. Un ejemplo es a través de la aplicación BlueCtrl que permite controlar todos los dispositivos que soporten Bluetooth mediante el uso de la pantalla táctil y el teclado del teminal Android como dispositivos de entrada.

Con él podremos controlar diferentes dispositivos como el iPad o la Playstation 3, e incluso el ordenador.

El único requisito para para poder utilizar BlueCtrl, es que es indispensable tener el terminal rooteado.
