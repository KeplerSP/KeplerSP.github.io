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
* Instituciones no capacitadas para emitir licencia de conducir.
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
◾ Tener un control directo sobre las instituciones encargadas de emitir licencias de conducir.  
◾ Tener conductores mejor capacitados al mejorar el sistema de emisión de carnets.  
◾ Reducir la cantidad de accidentes vehiculares al tener conductores más capacitados.  
◾ Disminuir la cantidad de vehiculos sin registrar.
## **Demostración del proyecto**
Al entrar a la página de inicio, se nos mostrará un buscador el cual los usuarios podrán usar para interactuar con el Smart Contract
y la información emitida por este.
![img-description](/assets/img/samples/1.png)
> Esta es una función que cualquier usuario puede utilizar por lo que no es necesario tener un monedero virtual instalado en el navegador.
  
Se mostrará la información de la matricula ingresada en caso haya sido registrada con anterioridad.
![img-description](/assets/img/samples/2.png)

Volviendo al menú de inicio, nos dirigiremos a la esquina superior derecha para entrar en modo "administrador" donde podremos registrar y editar información de las matriculas emitidas.
![img-description](/assets/img/samples/3.png)

##### Para poder usar las siguientes funciones es necesario tener Metamask instalado en el navegador.
![img-description](/assets/img/samples/4.png)
El contrato esta deplegado en la testnet de Polygon (Mumbai).  
Puedes obtener Matic de prueba en el siguiente link:  
<a href="https://mumbaifaucet.com/" target="_blank" rel="noreferrer">Mumbai Faucet</a>

Al dirigirnos a la pestaña **AGREGAR** tendremos un formulario. Todos los datos serán mandados al smart contract para luego ser emitidos en un evento.
![img-description](/assets/img/samples/5.png)
> La imagen será almacenada con IPFS y se guardará la referencia a esta dentro de un evento

En la pestaña **EDITAR** se encuentra un buscador para editar la información de la matricula que busquemos.
![img-description](/assets/img/samples/6.png)
![img-description](/assets/img/samples/7.png)
_En la parte superior de la página se mostrará la información de la matricula ingresada_
> Al ser este solo un prototipo ilustrativo solo se agregado la opción de agregar infracciones y vigencia del carnet.

Como dije antes este es solo un prototipo el cual sirve de manera ilustrativa para mostrar una ruta de operación de una web de registro vehicular descentralizado.
## **Detalles del código**
Dado que un smart contract no debe tratarse como si fuera una base de datos convencional, he optado por guardar en él simplemente un registro de direcciones autorizadas las cuales llamaré "administradores".  
Y el resto de información importante como matriculas agregadas o información editada será emitida como un evento, el cual podremos capturar posteriormente desde el Frontend y así obtener la información referente a la matricula.  
En esta ocasión he usado *Hardhat* y *ethers.js* para realizar las interacciónes con el smart contrat y la Blockchain.  
  
Como mencioné anteriormente los datos relacionados a una matricula serán emitidos como eventos y serán capturados en el FrontEnd con ethers.js para luego de un filtro minucioso, obtener los datos referentes a esa matricula. Esto además nos permite ahorrar gas ya que no estamos accediento a una función del smart contract para obtener sus datos.  

Al no haber necesidad de almacenar datos de la matricula en el contrato, nos limitamos a simplemente tener 2 funciones que trabajarán con los datos pasados desde el Frontend y luego agrupar esos datos y emitirlos en un evento.  
El código en Solidity también implementa librerias de OpenZepellin para aumentar su seguridad y eficiencia.

## **Cosas a mejorar**
Aún hay muchas más cosas que se podría implementar para hacer de esto un proyecto real que resuelva eficazmente el problema planteando.
* Lugar donde fue emitida la licencia de conducir.
* Puntos de sanción:  
Muchas instituciones tienen muy poco control y rigurosidad al evaluar a los estudiantes, dejando que muchas personas que no son aptas para conducir o no rinden adecuadamente el examen obtengan una licencia. Esto se podría controlar de esta forma:  
```
○ Alguien comete una infracción
○ Revisamos donde fue emitida su licencia
○ Agregamos puntos de sanción a la institución dependiendo la gravedad de la infracción
```
* Ocultar información sensible en caso el vehiculo sea de uso privado.
* Solo personal autorizado puede revisar un perfil privado.
* Compartir perfil del conductor (en caso sea público),etc.  

Pero el objetivo del proyecto es solo mostrar el potencial que posee la tecnología Web3, por ello he dejado de lado muchas posibles funcionalidades.

## **Conclusiones**
Gracias al uso de los contratos inteligentes junto a la cadena de bloques podemos crear herramientas realmente utiles que pueden ayudar a la sociedad más allá de sector económico.  
Si quieres probar la DApp, el link de abajo te redireccionará a la página en otra pestaña. Recuerda que es necesario usar **Metamask** para acceder a las opciones de Agregar y Editar matriculas.   

<a href="https://certificacion-descentralizada.netlify.app" target="_blank" rel="noreferrer">**REGISTRO DESENTRALIZADO**</a>