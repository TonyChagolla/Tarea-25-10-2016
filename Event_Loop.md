# Event Loop

A diferencia de Node.js, los motores de JavaScript para navegadores, tales como V8, unicamente cuentan con Heap y Stack, los cuales se encargan de asignar la memoria y de manejar los eventos que corren durante la ejecución respectivamente.

Javascript es un lenguaje de un solo hilo, esto quiere decir que solo hace una tarea a la vez, esto repesenta un problema al ejecutar este tipo de codigo en un navegador debido a que puede producir bloqueo.
Para solucinar este problema se hace uso de devoluciones de llamada asincrónicas (asynchronous callbacks). 

Para hacer uso de los callbacks se necesitan WebAPIs, las cuales mantienen el proceso de las callbacks hasta ser compleadas, una vez que fueron se completan. Mientras tanto el resto del codigo puede ser ejecutado sin que se se bloquee.

Una vez que los callbacks que se estan ejecutando en las WebAPIs son completadas, se agragan a una cola de tareas (task queue).
El event loop se encarga de revisar el stack para verificar que el stack este vacio, de ser asi, agrega el primer elemento que encuentre en la cola de tareas hasta que esta este vacia.

![Philip Roberts: What the heck is the event loop anyway? | JSConf EU 2014](https://i.makeagif.com/media/10-25-2016/KUTbdx.gif)
