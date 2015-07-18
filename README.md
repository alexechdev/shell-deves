# shell-deves
Una script para shell que realiza tareas cotidianas de una empresa en la que labore, el cual
utilizan vps no administrados como hostings.

Lo hago público para mostrar un ejemplo claro de como crear tu propio comando en shell
para optimizar algunas tareas en tu entorno de trabajo.

EL comando se llama deves y contiene las siguientes opciones
# "ci" utilizado para tareas de CodeIgniter

ejemplos:
```shell
deves ci instalar
```

```shell
deves ci generar controlador Inicio
```
o
```shell
deves ci -g controlador Inicio
```
más corto?
```shell
deves ci -g -c Inicio
```
Este genera un controlador en application/controllers/InicioController.php
```php
<?php defined('BASEPATH') OR exit('No direct script access allowed')

class Inicio extends CI_Controller {
    public function index()
    {
        //Código aquí
    }
}

```
###### InicioController.php

También si quieres generar los usados layouts header.php y footer.php
tan solo ejecuta
```shell
deves ci -g layouts
```
Este generara una carpeta layouts en la carpeta views y los archivos header.php y footer.php

```html
<!DOCTYPE html>
  <html lang="">
    <head>
    <meta charset="utf-8">
     <title>Mi web</title>
  </head>
<body>
```
###### header.php

Algunas otras pequeñas tareas como instalar apache y git, habilitar un sitio web para virtualhost.

Y por último el uso de algunos aliases
```shell
alias atras="cd .."
alias editar="deves -editar"
alias mostrar="deves -mostrar"
alias extraer="unzip"
alias salir="exit"
```
Acepto sus comentarios y dudas o algunas sugerencias para crear otros comandos.

# y ¿Cómo puedes realizar uno?
tan solo ve a la carpeta /usr/bin y crea un archivo con el nombre del comando que deseas.
```shell
sudo touch micomando
```
o
```shell
sudo nano micomando
```
sin ninguna extensión.

Dentro del archivo escribirmos en la primera linea
```shell
#!/bin/bash
```
Recuerden es muy importante esta linea ya que el sistema lo reconocera como un archivo shell, podemos agregar un comando simple como imprimir el famoso Hola Mundo.

```shell
#!/bin/bash

echo "Hola Mundo"
```

Antes de llamarlo le damos el permiso de ejecutable con el siguiente comando:
```shell
sudo chmod +x micomando
```
y probamos en nuestra consola:
```shell
$: micomando
Hola Mundo
```
Nota: el simbolo $: es solo referencia del usuario no lo uses en la ejecución de tu comando

Si no se ejecuta abre una nueva ventana en la terminal.

En el archivo deves puedes ver como hacer el uso de opciones en el comando, si tienes dudas en esto no dudes en mandarme un mensaje. 

