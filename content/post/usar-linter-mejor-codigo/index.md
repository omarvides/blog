---
title: "Usar un linter mejora tu código JavaScript"
date: 2017-07-22T12:49:07-06:00
coverImage:  assets/images/constellation.jpg
banner: assets/images/constellation.jpg
categories: ["JavaScript"]
tags: ["javascript", "desarrollo", "programación", "buenas prácticas"]
---

Utilizar un linter puede mejorar dramáticamente tu código JavaScript, puede ayudarte a 
escribir código mas limpio, mas fácil de entender y de mantener.

También te ayuda a estandarizar el código y fortalece el uso de un estilo, como consecuencia
mejora la forma en que los equipos colaboran en proyectos y la calidad de los mismos.

### Que hace un linter?

Un linter revisa tu código buscando errores y problemas de sintáxis, se asegura también que
el código que escribes siga un estilo, esto ayuda a que todo el código escrito en un proyecto se vea como
si hubiera sido escrito por la misma persona, y eso lo hace mas legible y mantenible.

------

### Configurar un linter para tu proyecto de NodeJS

Utilizaremos ESLint. Lo que necesitas para configurar ESLint para un proyecto de Node.JS es:

- Un plugin de ESLint para el editor que utilizas
- Dependencias de ESLint en tu proyecto de Node
- Archivo de configuración de ESLint
- El set de reglas de ESLint que quieres aplicar a tu código (En éste caso las de Airbnb)
- Instalar Yarn (Éste paso es opcional, yo utilizo yarn; pero en los lugares donde sea neceario voy a indicar como ejecutar los comandos con ```npm``` y con ```yarn```)

### Instalar yarn (Opcional)

- Éste paso es opcional, durante los pasos siguientes explico como instalar con ```npm``` y con ```yarn```

    ```bash
    npm install -g yarn
    ```

### Instalar ESLint

En el directorio de tu aplicación de Node, necesitarás instalar ESLint como dependencia de desarrollo

- Si prefieres utilizar yarn

    ```bash
    yarn add --dev eslint
    ```

- Si prefieres utilizar npm

    ```bash
    npm install --save-dev eslint
    ```

### Instalar eslint-config-airbnb (set de reglas de ESLint de airbnb)
    
- Utilizando ```yarn``` como manejador de paquetes

    ```bash
    npm info "eslint-config-airbnb@latest" peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs yarn add --dev "eslint-config-airbnb@latest"
    ```
- Utilizando ```npm``` como manejador de paquetes

    ```bash
    npm info "eslint-config-airbnb@latest" peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs npm install --save-dev "eslint-config-airbnb@latest"
    ```
*Qué es esto?* las últimas versiones de las dependencias de ```eslint-config-airbnb``` en el momento que escribo éste post están rotas, lo que hace éste comando es extraer la informacion en formato JSON de las dependencias de ```eslint-config``` y pasarlas como parámetro al comando ```yarn add``` o al comando ```npm install`` (según el caso) para instalar las versiones estables.

### Crear el archivo .eslint.json

- En la raíz de tu proyecto crea el archivo .eslint.json con el contenido

    ```json
    {
      "extends": "airbnb"
    }
    ```
Ésto le dice a ESLint que va a utilizar las reglas de airbnb.

### Instalando el plugin de ESLint en tu editor (Para Visual Code y Atom)

El paquete a instalar es un plugin de ESLint en tu editor preferido, los pasos por editor para acceder a la lista de paquetes son


### Acceder al manejador de paquetes (En Visual Code y Atom)

En Windows 

``` Ctrl + Shift + P```

En Mac

``` Cmd + Shift + P```

#### En Visual Studio Code en el cuadro de texto que aparece, escribir

```Extensions: Install Extensions```

#### En Atom Code en el cuadro de texto que aparece, escribir

```Install Packages And Themes```


#### Instalar ESLint

En Visual Code el paquete a instalar se llama ```eslint```.

En Atom el paquete a instalar se llama ```linter-eslint```. atom instalará o solicitara permiso para instalar las dependencias del paquete.


#### Usando ESLint

Una vez instalado en el editor si todos los pasos se hicieron correctamente, el plugin va a empezar a iluminar secciones del código que no cumplan con las reglas del linter de airbnb y necesiten ser cambiadas, como se muestra en las imagenes

*ESLint instalado en Atom*
{{< figure src="/assets/images/atom-eslint-in-action.png" width="100%">}}


*ESLint instalado en Visual Code*
{{< figure src="/assets/images/eslint-visual-code-in-action.png" width="100%">}}

#### Código fuente

El código fuente del ejemplo del post está en bajo el folder ejemplo-linter en el repository

https://github.com/omarvides/ejemplos-blog
