---
title: "Usar un linter mejora tu código JavaScript"
date: 2017-07-22T12:49:07-06:00
coverImage:  constellation.jpg
banner: constellation.jpg
categories: ["JavaScript"]
tags: ["javascript", "desarrollo", "programación", "buenas prácticas"]
---

Utilizar un linter puede mejorar dramáticamente tu código JavaScript, puede ayudarte a 
escribir código mas limpio, mas fácil de entender y de mantener.

Usar un linter te ayuda a estandarizar el código y fortalece el uso de un estilo, como consecuencia
mejora la forma en que los equipos colaboran en soluciones y proyectos y la calidad de los mismos.

### Que hace un linter?

Un linter revisa tu código buscando errores y problemas de sintáxis, se asegura también que
el código que escribes siga un estilo, esto ayuda a que todo el código escrito en un proyecto se vea como
si hubiera sido escrito por la misma persona, y eso lo hace mas legible y mantenible.

------

### Configurando un linter

Voy a explicar como configurar ESlint para un proyecto de Node.JS, lo necesario es:

- Un plugin de ESlint para el editor que utilizas
- Dependencias de ESlint en tu proyecto de Node
- Archivo de configuración de ESlint
- El set de reglas de ESlint que quieres aplicar a tu código (En éste caso las de Airbnb)
- Instalar Yarn (Éste paso es opcional, yo utilizo yarn; pero en los lugares donde sea neceario voy a indicar como ejecutar los comandos con ```npm``` y con ```yarn```)

### Instalar yarn (Opcional)

- Éste paso es opcional, durante los pasos siguientes explico como instalar con ```npm``` y con ```yarn```

    ```bash
    npm install -g yarn
    ```

### Instalar ESlint

En el directorio de tu aplicación de Node, necesitarás instalar eslint como dependencia de desarrollo

- Si prefieres utilizar yarn

    ```bash
    yarn add --dev eslint
    ```

- Si prefieres utilizar npm

    ```bash
    npm install --save-dev eslint
    ```

### Instalar eslint-config-airbnb (set de reglas de ESlint de airbnb)
    
- Utilizando ```yarn``` como manejador de paquetes

    ```bash
    npm info "eslint-config-airbnb@latest" peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs yarn add --dev "eslint-config-airbnb@latest"
    ```
- Utilizando ```npm``` como manejador de paquetes

    ```bash
    npm info "eslint-config-airbnb@latest" peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs npm install --save-dev "eslint-config-airbnb@latest"
    ```
*Qué es esto?* las últimas versiones de las dependencias de ```eslint-config-airbnb``` en el momento que escribo éste post están rotas, lo que hace éste comando es extraer la informacion en formato JSON de las dependencias de ```eslint-config``` y pasarlas como parámetro al comando ```yarn add``` o al comando ```npm install`` (según el caso) para instalar las versiones estables.

### Crear el archivo .eslintrc.json

- En la raíz de tu proyecto crea el archivo .eslintrc.json con el contenido

    ```json
    {
      "extends": "airbnb"
    }
    ```
Ésto le dice a eslint que va a utilizar las reglas de airbnb.

### Instalando el plugin de ESlint en tu editor

#### En Visual Studio Code

- 

#### En Atom

-

### En Sublime Text

- Con visual studio code abierto, presiona

En Windows 

``` Ctrl + Shift + P```

En Mac

- Ctrl/Cmd + Shift + P and then type Extensions: Install Extensions
- Look for ESlint pluging and install it


