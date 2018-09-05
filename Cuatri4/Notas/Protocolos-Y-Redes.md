# Protocolos y Redes

Profesor: Ing. Luis Manuel Morales Medina 

Cel. 3317388741

## Temario

### Modulo 1

1. Modelo OSI
2. Justificacion de un modelo de referencia
3. Capa Fisica
4. Capa de enlace
5. Capa de red
6. Capa de transporte
7. Protocoles TCP
8. Protocolo UDP
9. Analisis Comparativo TCP y UDP
10. Capa de que sision
11. Capa de presentacion
12. Capa de aplicacion

### Modulo 2

1. Modelo TCP IP
2. Capa de red
3. Capa de internet
4. Capa de transporte
5. Capa de aplicacion
6. Comparativa con el modelo OSI

### Modulo 3

1. Desarrollo de aplicaciones en red
2. Arquitectura cliente - servidor
3. Caracteristicas y responsabilidades del servidor
4. Implementacion de un servidor TCP
5. Caracteristicas y responsabilidades del cliente
6. Implementacion de un cliente TCP
7. Extendiendo el modelo para multiples clientes
8. Manejo de multiples estados
9. Arquitectura Peer to Peer (P2P)
10. Funcion del servidor en P2P
11. Caracteristicas de los clientes P2P

### Modulo 4

1. Desarrollo de juegos en red
2. Diferencias de diseño con un juego local
3. Planeacion de un juego en red
4. Diseño del protocolo a utilizar
5. Serializacion del estado
6. Sincronizacion del estado
7. Diseño de un servidor para multiplayer
8. Manejo de sesiones
9. Diseño de los clientes
10. Pruebas de un juego en red

## Evaluacion

- Parcial 1: Modulo 1 y 2
- Parcial 2: Modulo 3
- Parcial 3: Modulo 4

- Examen 30%
- Proyecto 30%
- Tareas 30%
- Ejercicios 10%

___

## Tema 1: Justificacion del modelo de referencia

La primera forma de comunicacione fue el telegrafo, el cual funcionaba por medio de pulsos, este solo podia ser utilizado de una persona a la vez ya que si no, los pulsos se distorcionaban.

La ISO (Organizacion Mundial de estandares) creo un modelo de referencia llamado OSI, este modelo funciona por medio de 7 capas que estan establecidas para el funcionamiento del mismo.

La justificacion es que simplemente se esta abstrayendo la manera de comunicacion para plasmarlo en una computadora.

#### TAREA 1:

#### Modelo OSI

Que es una red?

Se le llama red, a un conjunto de dispositivos o computadoras que estan conectados entre si, su finalidad es poder compartir recursos entre ellos que facilitan y optimizan las tareas del usuario.

Por los años 80 las redes crecian sin control, no existian ningun estandar para estas redes. Por lo tanto surge el modelo OSI, este modelo es creado por la ISO (Organizacion Internacional de estandarizacion), esta misma creo un estandar que se debe de seguir para que todas la empresas se puedan comunicar sin redes independientes.

En el modelo OSI existen 7 capas:

1. **Aplicacion:** Procesos de red a aplicaciones
   - Proporciona servicios de red a procesos de aplicacion (mail, ftp, ...)
2. **Presentacion: ** Representacion de datos
   - Asegura que el sistema receptor pueda leer los datos.
   - Formato de los datos.
   - Estructuras de los datos
   - Negociar la sintacis de transferencia de datos de la capa de aplicacion
3. **Sesión: ** Comunicacion entre host (equipos)
4. **Transporte: ** Comunicacion de extremo a extremo
   - Segmenta la infromacion en pequeños paquetes de datos TCP u UDP.
5. **Red: ** Direccionamiento y mejor ruta
6. **Enlace de datos: ** Acceso a los medios
7. **Física: ** Transmisión binaria

Se lee desde la capa superior hacia la inferior cuando el mensaje va a salir y desde la inferior a la superior cuando el mensaje va a entrar.

Este modela representa el conjunto de pasos que hace posible la comunicacion entre dispositivos.

#### Proyecto Arpanet

En 1968 el departamento de defensa de los estados unidos fue encargado de crear una red militar ya que temian que rusia los atacase y robara su informacion. Asi que se cre un departamento especial llamado "ARPA", esta crearia una red solida para proteger su informacion. 

Arpanet significa Red de la agencia de proyector de investigacion avancazada, BMN se encargo de realizar este proyecto mandando un mensaje de la universidad de california a la universidad de stanford ("Login"), tras dos años ya existian mas de 40 computadoras conectadas, para 1971 Ray Tomlinson crea un softer de envio - recepcion de correos electronicos, a las computadoras se les llamo procesadores de interfaz de mensajes (IMB), en 1972 arpanet se cambia el nombre a DARPA y se realiza la primera demostracion publica, en 1976 se establece el protocolo llamado x25 para la transmision de paquetes conmutados en redes oublicas, en 1981 IMB prensenta las primeras computadoras personales, vendiendo mas de 4000 computadoras en el primer mes.

En 1991 Robert Kaiju, quien ayudo con la realizacion de Arpanet decide ponerle al proyecto World Wide Web (WWW), en 1990  la sociedad se estaba conectando a arpanet pero no estaba diseñado para eso, por lo que se creo el protocolo TCP IP, despues de esto Arpanet se transformo en Internet, el cual facilito las interconecciones y dio origen a las graficas simple (imagenes), este nuevo protocolo hizo que creciera exponencialmente.

Arpanet esta creada principalmente para la proteccion de la informacion, sin embargo, se creo un beneficio mundial ya que fue el pionero de internet.

#### Implicaciones de la guerra fria y de la Segunda Guerra Mundial en la tecnologia

- Colossus: Fueron los primeros dispositivos calculadores electronicos usados por los britanicos para leer las comunicaciones cifradas de los alemananes. (Segunda Guerra)
- Cintan transportadora de papel: La maquina de Lorenz fue utilizada para cifrar comunicaciones militares alemandas de alto nivel durante la segunda guerra mundial.
- ENIAC (Electronic Numerical Integrator And Computer): Utilizada por el laboratorio de investigacion Balistica del ejercito de los Estados Unidos. Se considera la primera computadora de proposito general junto con colossus.
- Sputnik 1: Es el primer satelite artificial de la historia, crado por la union sovietica en 1957.
- NASA: Se crea en 1958 para la investigacion aeroespacial. 



#### TAREA 2: 

#### IEEE: Protocolo 802

IEEE (Institute of Electrical and Electronics Engineers) 802 es un proyecto que se identifica tambien por las siglas LMSC (LAN/MAN standard committee). Este se encarga de desarrollar estandares de red en area local (LAN) y redes de area metropolitana (MAN), este se encuentra en las dos capas inferiores del sistema OSI.

IEEE se manifiesta principalmente sobre las rede de computadora. Se refiere a IEEE 802 para referirse al estandar que se propone, algunos son:

- Ethernet (IEEE 802.3)
- Wi - Fi (IEEE 802.11)
- Bluetooth (IEEE 802.15), se esta intentando estandarizar.

Este se centra en subdividir el sugundo nivel, el de enlace, en dos sub niveles:

1. Enlace logico (LLC 802.2)
2. Control de acceso medio (MAC)

El resto de los estandares actuan en la capa fisica, como en el subnivel de acceso al medio.

En febrero de [1980](https://es.wikipedia.org/wiki/1980) se formó en el IEEE un comité de redes locales con la intención de estandarizar un sistema de 1 o 2 Mbps que básicamente era Ethernet (el de la época). Le tocó el número 802. Decidieron estandarizar el nivel físico, el de enlace y superiores. Dividieron el nivel de enlace en dos subniveles: el de enlace lógico, encargado de la lógica de re-envíos, control de flujo y comprobación de errores, y el subnivel de acceso al medio, encargado de arbitrar los conflictos de acceso simultáneo a la red por parte de las estaciones.

Para final de año ya se había ampliado el estándar para incluir el **Token Ring** ([red en anillo](https://es.wikipedia.org/wiki/Red_en_anillo) con paso de testigo) de [IBM](https://es.wikipedia.org/wiki/IBM) y un año después, y por presiones de grupos industriales, se incluyó [Token Bus](https://es.wikipedia.org/wiki/Token_Bus) ([red en bus](https://es.wikipedia.org/wiki/Red_en_bus) con paso de testigo), que incluía opciones de tiempo real y redundancia, y que se suponía idóneo para ambientes de fábrica.

Cada uno de estos tres "estándares" tenía un nivel físico diferente, un subnivel de acceso al medio distinto pero con algún rasgo común (espacio de direcciones y comprobación de errores), y un nivel de enlace lógico único para todos ellos.

Después se fueron ampliando los campos de trabajo, se incluyeron redes de área metropolitana (alguna decena de kilómetros), personal (unos pocos metros) y regional (algún centenar de kilómetros), se incluyeron redes [inalámbricas](https://es.wikipedia.org/wiki/Inal%C3%A1mbrico) ([WLAN](https://es.wikipedia.org/wiki/WLAN)), métodos de seguridad, comodidad, etc.

**Grupos de Trabajo**

|                                                              |                                                              |                            |
| ------------------------------------------------------------ | :----------------------------------------------------------- | -------------------------- |
| Nombre                                                       | Descripción                                                  | Nota                       |
| [IEEE 802.1](https://es.wikipedia.org/wiki/IEEE_802.1)       | Normalización de interfaz                                    |                            |
| [802.1d](https://es.wikipedia.org/wiki/IEEE_802.1D)          | *Spanning Tree Protocol*                                     |                            |
| [802.1p](https://es.wikipedia.org/w/index.php?title=IEEE_802.1P&action=edit&redlink=1) | [Asignación de Prioridades de tráfico](https://es.wikipedia.org/w/index.php?title=Asignaci%C3%B3n_de_Prioridades_de_tr%C3%A1fico&action=edit&redlink=1) |                            |
| [802.1q](https://es.wikipedia.org/wiki/IEEE_802.1Q)          | *Virtual Local Area Networks* ([VLAN](https://es.wikipedia.org/wiki/VLAN)) |                            |
| [802.1x](https://es.wikipedia.org/wiki/IEEE_802.1X)          | [Autenticación en redes LAN](https://es.wikipedia.org/w/index.php?title=Autenticaci%C3%B3n_en_redes_LAN&action=edit&redlink=1) |                            |
| [802.1aq](https://es.wikipedia.org/wiki/IEEE_802.1aq)        | [*Shortest Path Bridging* (SPB)](https://es.wikipedia.org/wiki/Shortest_Path_Bridging) |                            |
| [IEEE 802.2](https://es.wikipedia.org/wiki/IEEE_802.2)       | [Control de enlace lógico (LLC)](https://es.wikipedia.org/wiki/Control_de_enlace_l%C3%B3gico) | Activo                     |
| [IEEE 802.3](https://es.wikipedia.org/wiki/IEEE_802.3)       | [CSMA / CD](https://es.wikipedia.org/wiki/CSMA/CD) ([ETHERNET](https://es.wikipedia.org/wiki/Ethernet)) |                            |
| [IEEE 802.3a](https://es.wikipedia.org/w/index.php?title=IEEE_802.3a&action=edit&redlink=1) | Ethernet delgada 10Base2                                     |                            |
| [IEEE 802.3c](https://es.wikipedia.org/w/index.php?title=IEEE_802.3c&action=edit&redlink=1) | Especificaciones de Repetidor en Ethernet a 10 Mbps          |                            |
| [IEEE 802.3i](https://es.wikipedia.org/w/index.php?title=IEEE_802.3i&action=edit&redlink=1) | Ethernet de par trenzado 10BaseT                             |                            |
| [IEEE 802.3j](https://es.wikipedia.org/w/index.php?title=IEEE_802.3j&action=edit&redlink=1) | Ethernet de fibra óptica 10BaseF                             |                            |
| [IEEE 802.3u](https://es.wikipedia.org/wiki/IEEE_802.3u)     | Fast Ethernet 100BaseT                                       |                            |
| [IEEE 802.3z](https://es.wikipedia.org/w/index.php?title=IEEE_802.3z&action=edit&redlink=1) | Gigabit Ethernet parámetros para 1000 Mbps                   |                            |
| [IEEE 802.3ab](https://es.wikipedia.org/w/index.php?title=IEEE_802.3ab&action=edit&redlink=1) | Gigabit Ethernet sobre 4 pares de cable UTP Cat5e o superior |                            |
| [IEEE 802.3ae](https://es.wikipedia.org/w/index.php?title=IEEE_802.3ae&action=edit&redlink=1) | 10 Gigabit Ethernet                                          |                            |
| [IEEE 802.4](https://es.wikipedia.org/wiki/IEEE_802.4)       | Token bus LAN                                                | Disuelto                   |
| [IEEE 802.5](https://es.wikipedia.org/wiki/IEEE_802.5)       | Token ring LAN (topología en anillo)                         | Inactivo                   |
| [IEEE 802.6](https://es.wikipedia.org/wiki/IEEE_802.6)       | Redes de Área Metropolitana (MAN) (ciudad) (fibra óptica)    | Disuelto                   |
| [IEEE 802.7](https://es.wikipedia.org/w/index.php?title=IEEE_802.7&action=edit&redlink=1) | Grupo Asesor en Banda ancha                                  | Disuelto                   |
| [IEEE 802.8](https://es.wikipedia.org/wiki/IEEE_802.8)       | Grupo Asesor en Fibras Ópticas                               | Disuelto                   |
| [IEEE 802.9](https://es.wikipedia.org/wiki/IEEE_802.9)       | Servicios Integrados de red de Área Local (redes con voz y datos integrados) | Disuelto                   |
| [IEEE 802.10](https://es.wikipedia.org/wiki/IEEE_802.10)     | [Seguridad de red](https://es.wikipedia.org/wiki/Seguridad_inform%C3%A1tica) | Disuelto                   |
| [IEEE 802.11](https://es.wikipedia.org/wiki/IEEE_802.11)     | Redes inalámbricas WLAN. ([Wi-Fi](https://es.wikipedia.org/wiki/Wi-Fi)) |                            |
| [IEEE 802.12](https://es.wikipedia.org/w/index.php?title=IEEE_802.12&action=edit&redlink=1) | Acceso de Prioridad por demanda 100 Base VG-Any Lan          | Disuelto                   |
| [IEEE 802.13](https://es.wikipedia.org/w/index.php?title=IEEE_802.13&action=edit&redlink=1) | Se ha evitado su uso por superstición[2](https://es.wikipedia.org/wiki/IEEE_802#cite_note-2) | Sin uso                    |
| [IEEE 802.14](https://es.wikipedia.org/wiki/IEEE_802.14)     | Módems de cable                                              | Disuelto                   |
| [IEEE 802.15](https://es.wikipedia.org/wiki/IEEE_802.15)     | WPAN (Bluetooth)                                             |                            |
| [IEEE 802.16](https://es.wikipedia.org/wiki/IEEE_802.16)     | Redes de acceso metropolitanas sin hilos de banda ancha (WIMAX) |                            |
| [IEEE 802.17](https://es.wikipedia.org/wiki/IEEE_802.17)     | Anillo de paquete elástico script                            |                            |
| [IEEE 802.18](https://es.wikipedia.org/wiki/IEEE_802.18)     | Grupo de Asesoría Técnica sobre Normativas de Radio          | En desarrollo a día de hoy |
| [IEEE 802.19](https://es.wikipedia.org/wiki/IEEE_802.19)     | Grupo de Asesoría Técnica sobre Coexistencia                 |                            |
| [IEEE 802.20](https://es.wikipedia.org/wiki/IEEE_802.20)     | *Mobile Broadband Wireless Access*                           |                            |
| [IEEE 802.21](https://es.wikipedia.org/wiki/IEEE_802.21)     | Media Independent Handoff                                    |                            |
| [IEEE 802.22](https://es.wikipedia.org/wiki/IEEE_802.22)     | *Wireless Regional Area Network*                             |                            |



#### Porque no se estaba de acuerdo con el protocolo 802? 

Salio al mismo tiempo que la OSI.

#### Que es BPN? 

#### Firewall

## Tema 2: 

