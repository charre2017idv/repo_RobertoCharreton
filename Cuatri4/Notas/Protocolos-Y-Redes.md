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

#### Porque no se estaba de acuerdo con el protocolo 802? 

#### Que es BPN? 

#### Firewall

## Tema 2: 

