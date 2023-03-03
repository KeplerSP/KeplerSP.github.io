---
title: Registro Vehicular Descentralizado
categories: [DApp]
tags: [hardhat,ethers.js,react,ipfs]
---

## **Planteamiento del problema**
Es bien sabido por todos que la inseguridad social es un problema que esta muy presente en todo el mundo, especialmente en paises
no tan desarrollados como lo es el caso de Latinoamerica. Los asaltos, secuestros y accidentes vehiculares encabezan la lista como
los problemas más comunes en cuanto a delitos, los cuales son cometidos en su mayoria usando un vehiculo.
Las principales rázones son:
* Conductores no capacitados.
* Falta de rigor al realizar los exámenes de obtención de matricula.
* Instituciones no capacitadas para emitir carnets de conducir.
* Falsificación del carnet de conducir.
* Matriculas falsas o alteradas.
* Conductores con multiples papeletas al volante.
* Desconocimiento del pasajero sobre el perfil del conductor.

## **Presentación de la solución**
Aprovechando las carácterisiticas de los contratos inteligentes y la BlockChain he creado una DApp la cual sirve como prototipo
para una página que permita el registro y busqueda de matriculas, y la información relacionada a esta.  
**VENTAJAS:**  
◾ Transparencia de información entre el cliente y conductor.  
◾ Reducir el riesgo de un posible asalto o secuestro.  
◾ Gracias a la inmutabilidad de la cadena de bloques se tendrá un control más preciso y seguro sobre cada conductor.  
◾ Tener un control directo sobre las instituciones encargadas de emitir carnets de conducir.  
◾ Tener conductores mejor capacitados al mejorar el sistema de emisión de carnets.  
◾ Reducir la cantidad de accidentes vehiculares al tener conductores más capacitados.  
◾ Disminuir la cantidad de vehiculos sin registrar.
## **Demostración del proyecto**
Al entrar a la página de inicio, se nos mostrará un buscador el cual los usuarios podrán usar para interactuar con el Smart Contract
y la información emitida por este.
[IMAGEN]
> Esta es una función que cualquier usuario puede utilizar por lo que no es necesario tener un monedero virtual instalado en el navegador.
  
Se mostrará la información de la matricula ingresada en caso haya sido registrada con anterioridad.
[IMAGEN]

Volviendo al menú de inicio, nos dirigiremos a la esquina superior derecha para entrar en modo "administrador" donde podremos registrar y editar información de las matriculas emitidas.
[IMAGEN]

Al dirigirnos a la pestaña **AGREGAR** tendremos un formulario. Todos los datos serán mandados al smart contract para luego ser emitidos en un evento.[IMAGEN]
> La imagen será almacenada con IPFS y se guardará la referencia a esta dentro de un evento

En la pestaña **EDITAR** se encuentra un buscador para editar la información de la matricula que busquemos.[IMAGEN]
> Al ser este solo un prototipo ilustrativo solo se agregado la opción de agregar infracciones y vigencia del carnet.

Como dije antes este es solo un prototipo el cual sirve de manera ilustrativa para mostrar una ruta de operación de una web de registro vehicular descentralizado.
## **Detalles del código**
Dado que un smart contract no debe tratarse como si fuera una base de datos convencional, he optado por guardar en él simplemente un registro de direcciones autorizadas las cuales llamaré "administradores".  
Y el resto de información importante como matriculas agregadas o información editada será emitida como un evento, el cual podremos capturar posteriormente desde el Frontend y así obtener la información referente a la matricula.  
En esta ocasión he usado *Hardhat* y *ethers.js* para realizar las interacciónes con el smart contrat y la Blockchain.  
  
Como mencioné anteriormente los datos relacionados a una matricula serán emitidos como eventos y serán capturados en el FrontEnd con ethers.js para luego de un filtro minucioso, obtener los datos referentes a esa matricula. Esto además nos permite ahorrar gas ya que no estamos accediento a una función del smart contract para obtener sus datos.  

Al no haber necesidad de almacenar datos de la matricula en el contrato, nos limitamos a simplemente tener 2 funciones que trabajarán con los datos pasados desde el Frontend y luego agrupar esos datos y emitirlos en un evento.  
El código en Solidity también implementa librerias de OpenZepellin para aumentar su seguridad y eficiencia.

>"LINK AL CONTRATO"

## **Cosas a mejorar**
Lugar donde fue emitido
Puntos de sanción
s
## **Conclusiones**
[**PROBAR DAPP**](https://certificacion-descentralizada.netlify.app)