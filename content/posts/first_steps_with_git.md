---
title: "Iniciando con Git"
date: 2022-04-13 T18:16:21-06:00
description: 'Primeros Pasos con Git.'
---

Imagina trabajar en un proyecto al cual le has invertido mucho tiempo y esfuerzo, puede ser un código de programación, un proyecto de photoshop, etc.  

Pero, ¡sorpresa!, resulta que hay un error en tu código y al hacer modificaciones has terminado modificando el funcionamiento de una sección, o imagina que has borrado una carpeta con
capas sin querer y has cerrado el proyecto. Probablemente te haya pasado alguna vez algo parecido, y todos sabemos que esto no es nada agradable ni divertido.

Quizá podríamos hacer carpetas para ir realizando copias de tu proyecto, pero probablemente acabemos con muchas de ellas y exoste el riesgo que guardemos parte de la nformación
en una carpeta que no era la correcta. ¿Existirá alguna mejor forma de hacer respaldos y tener segura nuestra información?. La respuesta es si, utilizar Git.
Git es un sistema de control de versiones que nos ayudará a tener respaldos de nuestro trabajo, regresarlos a un punto en el que nuestro proyecto servía, compartirlo
con nuestros colaboradores entre muchas, muchas otras cosas más.

## ¿Qué es un control de versiones?

Ahora sabemos que Git es un control de versiones, pero ¿con qué se come eso?.

Un control de versiones es un sistema que se encarga de registrar todos los cambios que vas realizando en los archivos de tus proyectos, de forma que si a tu cliente le gustaba
más la primera paleta de colores en tu diseño o necesitas la última versión de tu código que servía mejor de lo que la actual lo hace podrás recuperar todo ello en unos pocos segundos.
Permite comparar los cambios hechos a lo largo del tiempo, ver quien modificó por última algún archivo que te esta dando problemas, cuando lo hizo y mucho más.

## Fundamentos de Git

Llamemos a partir de ahora a los sistemas de control de versiones por sus siglas en inglés: **VCS** (Version Control Systems).
La diferencia de Git con cualquier otro VCS es como manejan sus datos. Para entender esto, dígamos que es como si Git tomará una foto cada vez que guardas tu archivo y guarda
una referencia a esa foto. En caso de que existan archivos en un proyecto que no han sido modificados Git no tomará una nueva foto, dejará la última que tomo porque ese
archivo sigue igual.

Gran parte de las operaciones que hace Git se hacen de forma local, sin tener que conectarte a internet, toda la historia de tu proyecto se queda en tu disco local, por lo que
la mayoría de sus operaciones son inmediatas. 
Git utiliza una suma de comprobación, conocida también como [checksum](https://www.wikiversus.com/informatica/que-es-checksum/) para verificar e identificar el contenido.
Por lo tanto no es posible cambiar dicho contenido sin quer Git lo sepa. Para ello Git utiliza un mecánismo conocido como hash SHA-1, una cadena de 40 caracteres hexadecimales
(0-9, A-F) calculada en base al contenido del archivo o la estructura del directorio en Git.
Un hash SHA-1 se ve así:  

**12CE7981109FD2FBDE7C4816AA184EC2A9CC10C7**

Estos valores los podrás ver mucho en Git ya que todo se guarda por el valor hash de sus contenidos

## Los 3 estados

Esto es muy importante de recordar, Git tiene tres estados principales en los que se pueden encontrar tus archivos:

- **Commited**(Confirmado): Los datos han sido almacenados de forma segura 
- **Modified**(Modificado): Has modificado un archivo, pero no lo has confirmado
- **Staged**(Preparado): Has marcado un archivo modificado para ser confirmado

Esto nos lleva a las 3 secciones principales de un proyecto de Git:

- **Git directory**(Directorio de Git):Se almacenan los metadatos y la base de datos de objetos para tu proyecto, la parte más importante de Git y lo que se copia 
cuando clonas un repositorio de otra computadora.
- **Working directory**(Directorio de trabajo):Copia de una versión del proyecto, se sacan de la base de datos comprimida en el Git directory y se colocan en tu disco para que los puedas usar o modificar
- **Staging area**(Área de preparación):Es un archivo generalmente contenido en el directorio de Git que guarda información sobre que es lo que vas a incluir en tu siguiente confirmación (commit)

Flujo de trabajo:

1. Modificas una serie de archivos en tu directorio de trabajo
2. Preparas los archivos, añadiendolos a tu área de preparación
3. Confirmas los cambios, lo que toma los archivos tal y como estan en el área de preparación y almacena esa copia de forma permanente en tu directorio de Git

Si una versión concreta de un archivo está en el directorio de Git se considera *confirmada(committed)*. Si ha sufrido cambios desde que se obtuvo el repositorio pero la has añadido
al área de preparación esta *preparada(staged)*, si por otro lado no se ha preparado está *modificada*

