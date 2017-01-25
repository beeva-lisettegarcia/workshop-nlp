# Demostración MS-LUIS



## Preconfiguración:

Crear cuenta de usuario.
Crear aplicación nueva.

## Ej 1: *consultar vuelos*
Crear entidad “location”, con entidades hijas “location_to” y “location_from”.
Se crean las intenciones “consultar_vuelos”.

#### Primera versión
Se añade la frase “dime vuelos a Roma”, marcando Roma como entidad location_to.
Se añade la frase “dime vuelos para Viena”, marcando Viena como entidad location_to.
Se añade la frase “dime vuelos a Londres desde Madrid”, marcando Londres como entidad location_to y Madrid como entidad lcoation_from.
Se añade la frase “dime vuelos desde Oslo a Viena”, marcando Oslo como location_from y Viena como entidad lcoation_to.

Se pulsa el botón “train”, abajo a la izquierda.
Se prueba la frase “dame vuelos para Barcelona desde Valencia”

#### Más mejoras
Se añade diversidad a la frase

Se añade la frase “quiero ir a helsinki”, marcando helsinki como location_to 
Se pulsa el botón train
Se prueba la frase “cuanto me cuesta ir a oslo”

## Ej 2: *consultar vuelos baratos*
Añadir precio

Añadir intención “ “consultar_vuelos_baratos”.
Crear la entidad interna “money” de tipo money.

Se añade la frase “dime vuelos por menos de 50€”, se marca 50€ como money automáticamente y se asigna al intent consultar_vuelos_baratos
Se prueba la frase “dime vuelos por menos de 60€ a roma”, se ve que el intent está mal clasificado. Se clasifica correctamente
Se añade “dime vuelos a riga por menos de 40€ desde londres”, se ve que está mal la intención. Se clasifica correctamente

Se pulsa el botón train.

## Ej 3: *añadiendo fechas*
Añadir fechas
Crear entidad interna “datetime” de tipo datetime

Se prueba la frase “dime vuelos para el 3 de enero de 2016 por menos de 40€ a riga desde roma”, se ve que coge la palabra “el” como destino. Se desmarca la palabra “el” como entidad y se marca riga como entidad location_to.
Se prueba la frase “dime vuelos para el 3 de enero de 2016 por menos de 40€ para riga”
Se pulsa el botón train.

Se prueba la frase “dime vuelos para el 3 de enero de 2016 por menos de 40€ para riga”
Se prueba la frase “dime vuelos para el 5 de mayo de 2016 para helsinki”. Se muestra que no reconoce las entidades. Se marcan adecuadamente.

## Ej 4: *añadiendo listas*
Se añaden phrase list
Se añaden a la phrase list el grupo “ciudades” con la cadena: las palmas, palma de mallorca, san sebastián
Se prueba la frase “quiero ir el 5 de enero de 2016 a las palmas”
Se prueba la frase “quiero ir hoy a las palmas”, se ve que reconoce hoy como fecha
Se prueba la frase “quiero ir mañana a las palmas”, se ve que no reconoce mañana como fecha

