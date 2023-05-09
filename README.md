# mqtt-chat-publico
Este repositorio contiene las instrucciones para hacer un chat publico muy simple con Mosquitto MQTT y la terminal de Ubuntu

# Introducción

En este ejercicio se realizará un chat publico con Mosquitto MQTT en la terminal de Linux. Este ejercicio forma parte del curso de MQTT de [codigoiot.com](https://codigoiot.com).

## Alcance

Este curso se realiza por completo en la terminal. No se requiere desarrollar una aplicación. No es uno de los objetivos de este ejercicio generar un chat permanente, sino que se se busca ejemplificar el uso básico de los comandos de terminal de mosquitto.

# Requisitos

A continuación se muestran los requisitos necesarios para realizar este ejercicio

## Software necesario

- Linux. Se recomienda cualquier versión de [Ubuntu LTS](https://ubuntu.com/download/desktop)
- [Mosquitto MQTT](https://mosquitto.org/download/)
- mosquitto-clients

## Material de referencia

- [Instalación de Virtual Box en  OS X](https://edu.codigoiot.com/course/view.php?id=820)
- [Instalación de Virtual Box en Windows](https://edu.codigoiot.com/course/view.php?id=810)
- [Instalación de Ubuntu en Virtual Box](https://edu.codigoiot.com/course/view.php?id=812)
- [Instalación de Mosquitto MQTT](https://edu.codigoiot.com/course/view.php?id=818)
- [Introducción a MQTT](https://edu.codigoiot.com/course/view.php?id=851)

## Servicios

Para la realización de este ejercicio se requiere de un broker publico. A continuación se presenta una lista de opciones.

- [test.mosquitto.org](https://test.mosquitto.org/)
- [broker.hivemq.com](http://www.mqtt-dashboard.com/#)

En este ejercicio se usa hivemq.

# Instrucciones

## Requisitos previos

Para realizar este ejercicio se requiere contar con lo siguiente

1. Debes tener Mosquitto Instalado. Para ello, usa el siguiente comando.

    ```sudo apt-get install mosquitto```

2. Debes tener instaldo __dnsutils__, para ello, usa el siguiente comando

    ```sudo apt install dnsutils```

3. Necesitas el cliente de mosquitto. Para instalarlo, usa el siguiente comando.

    ```sudo apt-get install mosquitto-clients```

## Preparaicpon de entorno

Para este ejercicio necesitas lo siguiente

- Abrir una terminal para el suscriptor. Esta terminal recibirá los mensajes.

- Abrir una terminal para publicar. Esta terminal enviará los mensajes.

En total necesitarás dos terminales.

## Instrucciones de operación

Para ejecutar este ejercicio deberas realizar lo siguiente

1. Obten la ip del broker publico con el comando ```nslookup broker.hivemq.com```

2. Suscribete al tema del ejercicio con el siguiente comando

    ```mosquitto_sub -h broker.hivemq.com -t codigoIoT/chat```

    __Nota__: Si usas una IP en el host (opción -h), asegurate de que todas las personas en el chat usen la misma IP.
    
    __Nota__: Esta terminal será dedicada para recibir mensajes
    
    __Nota__: Al principio parecera que no pasa nada, debes esperar a que llegue un mensaje, lo que se realizará en el siguiente ejercicio.
3. En una nueva terminal, envía un mensaje de prueba. Usa el siguiente  comando.
    
    ```mosquitto_pub -h broker.hivemq.com -t codigoIoT/chat -m "$(whoami): Hola mundo!"```

# Resultado

A continuación puedes ver imagenes del resultado esperado

