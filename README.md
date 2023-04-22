# Flow4-NodeRed
Este es el cuarto ejercicio con NodeRed

## Introducción

El flow 4 realizado con NodeRed y consiste en enviar la temperatura y la humedad por un nodo mqtt. 

## Material Necesario

Para realizar este flow necesitas lo siguiente:

- [Ubuntu 20.04](https://releases.ubuntu.com/20.04/)
- [NodeJS](https://nodejs.org/es/)
    - NPM
    - NodeRed
    - Nodos Dashboard

## Material de referencia

En los siguientes enlaces puedes encontrar cursos en la plataforma de edu.codigoiot.com que te permitirán realiar las configuraciones necesarias

- [Instalación de Virutal Box y Ubuntu 20.04](https://edu.codigoiot.com/course/view.php?id=812)
- [Instalación de NodeRed](https://edu.codigoiot.com/course/view.php?id=817)
- [Introducción a NodeRed](https://edu.codigoiot.com/course/view.php?id=278)
- [Introducción a MQTT](https://edu.codigoiot.com/enrol/index.php?id=851)

## Instrucciones

### Requisitos previos

Para que este flow funcione, debes cumplir con los siguientes requisitos previos

1. Instalación de NodeJS. Se recomienda tener instalado NodeJS en alguna versión LTS. Al momento de creación de este documento, se usó la versión 18.12LTS. Esta instalación debe incluir las Build-Tools para hacer uso de NPM
2. Instalación de NodeRed. La instalación se realiza por NPM. Al momento de la creación de este contenido, se usó la versión 3.0.2

### Instrucciones de preparación del entorno

Para ejecutar este flow es necesario lo siguiente: 
- Arrancar NodeRed con el comando node-red
- Una vez dentro agregar los nodos siguientes: 1 nodo mqtt in, 1 nodo json, 2 nodos function, 2 nodos gauge y un nodo chart.
- Se agregará el nombre del servidor a localhost:1883 y el topic a codigoIoT/Mor/mqtt/flow4
- El nodo json se cambiara a la opcion de convertir objetos javascript
- El nodo function 1 será Temperatura y agregar un codigo msg.payload = msg.payload.temp; msg.topic = "Temperatura"; return msg;
- El nodo 2 será Humedad y agregar el codigo msg.payload = msg.payload.hum; msg.topic = "Humedad"; return msg; en ambos nodos se agregan en la pestaña "on message"
- Agregar una tabla y cambiar al nombre de flow4 y dentro agregar 3 grupos que se llamen temperatura, humedad e historico y relacionarlos con los grupos que se crearon. 
- Hacer clic en el botón Deploy.


### Instrucciones de operación

Para observar el resultado de este flow, sólo es necesario abrir el navegador y escribir la siguiente dirección http://localhost:1880/ui y dentro de la página hay un menú derecho y hacer clic en flow4, debemos abrir la terminal para poder mandar una instrucción y el resultado se muestra en el navegador. 
mosquitto_pub -h localhost -t codigoIoT/Mor/mqtt/flow4 -m '{"id":"Diana","temp":16,"hum":51}' 

## Resultados

A continuación puede verse una vista previa del resultado de este flow.

![](https://github.com/LauraGx/Flow4-NodeRed/blob/main/flow4.png)
![](https://github.com/LauraGx/Flow4-NodeRed/blob/main/flow4.2.png)

# Créditos

Desarrollado por Diana Laura Aragon

- [GitHub](https://github.com/LauraGx)

