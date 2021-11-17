author: David Valenzuela Vargas
summary: Bastionado de arranque del sistema Lenovo.
id: bastionado-lenovo-bios-uefi
categories: bios, uefi, lenovo
environments: Web
status: Published
feedback link: 

# Bastionado de arranque del sistema

## Protección de la BIOS/UEFI

La BIOS o UEFI, es nuestro primer programa que ejecuta nuestros ordenador al iniciarse. La función que este con lleva es la de recordar al dispositivo quién es, el hardware que contiene y lo primero que debe arrancar.

Existen varios parámetros que podremos configurar para asegurar en mayor medida nuestra BIOS o UEFI.

Los más comunes son los siguientes:

* Contraseña de administración de la BIOS: Si se activa, solicitará una contraseña para modificar los parámetros de la BIOS.

* Contraseña de arranque del dispositivo (también llamada contraseña de usuario o Power-On): Si se activa, solicitará una contraseña para poder arrancar el equipo. Esta opción no suele utilizarse en servidores, ya que si el equipo se reinicia o se intenta encender a través de la red (Wake on LAN o WoL), no arrancaría los servicios hasta que se pusiese manualmente la contraseña.

* Permiso para el arranque desde dispositivos USB: Si está deshabilitado, no se podrá arrancar el ordenador desde unidades extraíbles a través del puerto USB.

* Orden de arranque: Define el orden en el que se produce el arranque del sistema. Cuando el dispositivo se inicie, buscará un posible arranque en el primer dispositivo que se indique, si no lo encuentra, lo intentará en el segundo, y así sucesivamente.

* Secure Boot: Introducido por Microsoft a partir de Windows 8, deniega la ejecución en el arranque de software no firmado y, en general, prohíbe la ejecución de cualquier cosa que no sea Windows. Algunas distribuciones Linux se han ido adaptando para que también se permita su ejecución.

Pero, ¿Es totalmente seguro aún configurando todas estas opciones?.

No existe nada con una seguridad al 100%, en lo siguientes casos podremos observar algunos problemas:

* En una grama de placas bases, apenas con quitar y volver a poner la pila de botón conseguiremos que se elimine toda la configuración previo de la BIOS y vuelva a tener los valores por defecto. En otras BIOS es posible realizar un cortocircuito en unos pines determinados de la placa y de esta manera resetearla. En este tipo de casos, la úniica solución quen tendremos es la de proteger los equipos físicamente para impedir el acceso mediante carcasas con llave, por ejemplo.

Tenemos que recordar que no es necesariamente necesario encender el equipo, ya que teniendo la facilidad de acceso de manera física podríamos retirar los discos duros, actualmente muy pocas placas bases pueden configurarse para evitar ser reseteadas, existe una opción que traen algunos modelos en los que guardan la contraseña de arranque en una memoria non volátil, en este tipo de modelos resetear la BIOS no será útil para acceder al equipo, ya que este lo primero que solicita al arrancar es la contraseña en esa ubicación.


## Guía para bastionado de BIOS/UEFI en Lenovo Z50

Para tener acceso al menú BIOS en este dispositivo debemos acceder pulsando F1 al pulsar el botón de encendido.

## Contraseña de arranque

Una vez dentro del menú BIOS de nuestro ordenador, debemos de desplazarnos a la sección de **"Security"** nos aparecerá en segundo lugar listado la opción de habilitar una contraseña de arranque **"User password"**, una vez pulsemos sobre esta, nos mostrará otra nueva pequeña ventana en la que introducimos una nueva contraseña y su confirmación. Una vez realizado el ajuste nos dirigimos a la pestaña **"Exit"** y guardamos los cambios realizados, a partir de ahora, a cada inicio nos requerirá la contraseña que previamente asignamos. Esto es más seguro pero no es lo más ideal a la hora de trabajar de forma remota con equipos mediante **"Wake On Lan"** ya que tendremos que estar de forma presencial delante del equipo para introducir la contraseña si en algún caso el equipo se apagase.

![Power On BIOS](image/power_on-lenovo.jpg)

## Contraseña de administrador

En este apartado que se encuentra justo en primer lugar antes de la anterior opción mencionada, tenemos la posibilidad de habilitar otra opción de seguridad que se trata de algo similar a la anterior, pero esta nos ofrece el integrar una contraseña de administrador para evitar que cualquier otra persona que desconozca la contraseña, tenga la posibilidad de modificar los ajustes de nuestra BIOS. El proceso de habilitación es el mismo, nos dirigimos a la pestaña de **"Security"** y en la primera opción **"Administrator password"** pulsamos intro sobre esta y nos requerira una nueva contraseña y confirmación, guardamos y salimos de nuestro menú BIOS.

![Admin password](image/admin_pass-lenovo.jpg)

## Arranques externos

Para evitar arranques de programas externos al equipo mediante USB booteables, o SO operativos grabados en CD y pudiendo ser arrancados desde la CD-ROM o incluso mediante Red, todos estos parámetros podremos desactivarlos en el apartado de **"Boot"**, simplemente con pulsar "Enter" sobre ellos nos ofrecerá la opción de desactivarlos o activarlos.

![Arranques externos](image/arranques_externos-lenovo.jpg)

## Orden de arranque

En esta misma pestaña un poco más abajo nos encontramos la opción de **"EFI"** desde donde podremos priorizar el arranque desde el dispositivo que tengamos con mayor preferencia, este se ordena de arriba a hacia abajo, teníendo como primera prioridad el lugar número 1 y como último el final de la lista.

![Orden de arranque](image/orden_arranque-lenovo.jpg)

## Otras opciones de Seguridad

Cómo otras opciones de seguridad tenemos la opción de **"Secure Boot"** que se encuentra en la pestaña de **"Security"**, esta opción lo que evita es poder iniciar en nuestro equipo cualquier software que no esté firmado y por lo general rechazar el arranque a todo aquel sistema operativo ajeno a Windows, existen distribuciones de Linux que están adaptadas a este tipo de casos para poder iniciarse sin problemas.

(FOTO)