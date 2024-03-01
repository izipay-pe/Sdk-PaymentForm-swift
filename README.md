# [Sdk-PaymentForm-Swift]
##  Índice
* [1. Introducción](#1-introducción)
* [2. Requisitos previos](#2-requisitos-previos)
* [3. Despliegue](#3-despliegue)
* [4. Datos de conexión](#4-datos-de-conexión)
* [5. Transacción de prueba](#5-transacción-de-prueba)
* [6. Implementación de la IPN](#6-implementación-de-la-ipn)
* [7. Consideraciones](#7-consideraciones)
## 1. Introducción
En este manual podrás encontrar una guía paso a paso para configurar un proyecto de **[Swift]** con la pasarela de pagos de IZIPAY. Te proporcionaremos instrucciones detalladas y credenciales de prueba para la instalación y configuración del proyecto, permitiéndote trabajar y experimentar de manera segura en tu propio entorno local.
Este manual está diseñado para ayudarte a comprender el flujo de la integración de la pasarela para ayudarte a aprovechar al máximo tu proyecto y facilitar tu experiencia de desarrollo.

<p align="center">
  <img src="https://github.com/izipay-pe/Imagenes/blob/main/formulario_movil_sdk/apple1.png" alt="Formulario" width="250"/>
  
</p>
<a name="Requisitos_Previos"></a>
 
## 2. Requisitos previos
* Comprender el flujo de comunicación de la pasarela. [Información Aquí](https://secure.micuentaweb.pe/doc/es-PE/rest/V4.0/javascript/guide/start.html)
* Extraer credenciales del Back Office Vendedor. [Guía Aquí](https://github.com/izipay-pe/obtener-credenciales-de-conexion)
* Solicitar la habilitación de API REST: **Pago a tráves de un SDK móvil para Android o IOS**
* Para este proyecto utilizamos la herramienta XCode.
* Tener instalado CocoaPods
> [!NOTE]
> Tener en cuenta que, para que el desarrollo de tu proyecto, eres libre de emplear tus herramientas preferidas.

## 3. Despliegue

### Clonar el proyecto:
  ```sh
  git clone [https://github.com/izipay-pe/Sdk-PaymentForm-swift.git]
  ```
### Ejecutar proyecto

En la carpeta principal del proyecto, instalamos las dependencias usando CocoaPods. Abrimos la terminal, nos dirigimos a la carpeta y ejecutamos el comando `pod update`

<p align="center">
  <img src="https://i.postimg.cc/XNDfYS3N/podupdate.png" alt="Run"/>
</p>


Abrir el proyecto con el archivo `.xcworkspace`


<p align="center">
  <img src="https://i.postimg.cc/FKQwzVC9/carpeta.png" alt="Run"/>
</p>

## 4. Datos de conexión 

**Nota**: Reemplace **[REMPLACE_ME]** con sus credenciales de `API REST` extraídas desde el Back Office Vendedor, ver [Requisitos Previos](#Requisitos_Previos).

* Editar en `AppDelegate` :
  
  `publicKey` : Reemplazar por tu clave pública que puedes encontrar en tu Back Office Vendedor.
  
  `apiServerName` : Reemplazar por el nombre del servidor API REST que puedes encontrar en tu Back Office Vendedor.
  
<p align="center">
  <img src="https://i.postimg.cc/X7LR2z8t/appdelegate.png" alt="Credentials"/>
</p>

* Editar en `ServerCommunication` :

  `kMerchantServerUrl` : Reemplazar por la URL del servidor del comercio.
  
  `username` : Reemplazar por el usuario que puedes encontrar en tu Back Office Vendedor.

  `password` : Reemplazar por la contraseña que puedes encontrar en tu Back Office Vendedor.

  
<p align="center">
  <img src="https://i.postimg.cc/RhysDhG0/servercomunication.png" alt="Credentials"/>
</p>

## 5. Transacción de prueba
Antes de poner en marcha su pasarela de pago en un entorno de producción, es esencial realizar pruebas para garantizar su correcto funcionamiento. 

Puede intentar realizar una transacción utilizando una tarjeta de prueba en el botón flotante de Test (en la parte superior derecha de la demo).

<p align="center">
  <img src="https://github.com/izipay-pe/Imagenes/blob/main/formulario_movil_sdk/apple2.png" alt="Test" width="250"/>
</p>

* También puede encontrar tarjetas de prueba en el siguiente enlace. [Tarjetas de prueba](https://secure.micuentaweb.pe/doc/es-PE/rest/V4.0/api/kb/test_cards.html)
 
## 6. Implementación de la IPN
> [!IMPORTANT]
> Es recomendable implementar la IPN para comunicar el resultado de la solicitud de pago al servidor del comercio.

La IPN es una notificación de servidor a servidor (servidor de Izipay hacia el servidor del comercio) que facilita información en tiempo real y de manera automática cuando se produce un evento, por ejemplo, al registrar una transacción.
Los datos transmitidos en la IPN se reciben y analizan mediante un script que el vendedor habrá desarrollado en su servidor.
* Ver manual de implementación de la IPN. [Aquí]( https://secure.micuentaweb.pe/doc/es-PE/rest/V4.0/kb/payment_done.html)
* Vea el ejemplo de la respuesta IPN con PHP. [Aquí](https://github.com/izipay-pe/Redirect-PaymentForm-IpnT1-PHP)
* Vea el ejemplo de la respuesta IPN con NODE.JS. [Aquí](https://github.com/izipay-pe/Response-PaymentFormT1-Ipn)


## 7. Consideraciones
Para obtener más información, echa un vistazo a:
- [Formulario incrustado: prueba rápida](https://secure.micuentaweb.pe/doc/es-PE/rest/V4.0/javascript/quick_start_js.html)
- [Primeros pasos: pago simple](https://secure.micuentaweb.pe/doc/es-PE/rest/V4.0/javascript/guide/start.html)
- [Servicios web - referencia de la API REST](https://secure.micuentaweb.pe/doc/es-PE/rest/V4.0/api/reference.html)
