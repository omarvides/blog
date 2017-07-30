---
title: "Usar un linter mejora tu código JavaScript"
date: 2017-07-22T12:49:07-06:00
coverImage:  https://raw.githubusercontent.com/omarvides/blog/master/docs/post/usar-linter-mejor-codigo/constellation.jpg
banner: https://raw.githubusercontent.com/omarvides/blog/master/docs/post/usar-linter-mejor-codigo/constellation.jpg
categories: ["JavaScript"]
tags: ["javascript", "desarrollo", "programación", "buenas prácticas"]
---

Utilizar un linter puede mejorar dramáticamente tu código JavaScript, puede ayudarte a 
escribir código mas limpio, mas fácil de entender y más facil de mantener.

Usar un linter te ayuda a estandarizar el código y enforza el uso de un estilo, como consecuencia
mejora la forma en que los equipos colaboran en soluciones y proyectos y la calidad de los mismos.

### Que hace un linter de JavaScript?

Un linter de JavaScript revisa tu código buscando errores y problemas de sintáxis, se asegura también que
el código que escribes siga con un estilo, esto causa que todo el código escrito en un proyecto se vea como
escrito por la misma persona, y eso lo hace mas legible y mantenible.



# Eslint instalation steps

## Install yarn

```bash
npm install -g yarn
```

## Install eslint
```bash
export PKG=eslint-config-airbnb
npm info "$PKG@latest" peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs yarn add --dev "$PKG@latest"
```

## Create the .eslintrc file

with content 
```json
{
  "extends": "airbnb"
}
```

## Install Visual code plugin

- Ctrl/Cmd + Shift + P and then type Extensions: Install Extensions
- Look for ESlint pluging and install it


