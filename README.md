## PASOS PARA AGREGAR UN PROYECTO VUE Y SUBIRLO A GITHUB PAGE

- Paso 1. Crear proyecto de VUE CLI (Agregar vuex/router si es necesario)

- Paso 2. Crear el repositorio en GitHub y sincronizarlo con el proyecto local

- Paso 3. Agregar la siguiente linea de comando a vue.config.js (El proyecto actual es VUE 3)

```javascript
module.exports = defineConfig({
  transpileDependencies: true,
  publicPath: process.env.NODE_ENV === 'production' ? '/gitpagepruebafinal3/' : '/'
})
```
>[!IMPORTANT]
>Debemos modificar la ruta y agregar la del github, yo realice una prueba en el cual eran diferentes y no me funcionaba

-  Paso 4. Luego de haber realizado lo mencionado debemos agrear el siguiente comando a la terminal

```bash
  npm run build
```
Esto creara la carpeta "dist" con el proyecto actualizado (Basicamente compila el proyecto y lo sube en una carpeta)

-  Paso 5. Agrega los archivos generados en la carpeta dist al área de preparación (staging area) de Git con el comando

```bash
  git add dist -f
```
Lo puedes agregar 2 veces si es necesario, algunass veces lanza una alerta

-  Paso 6. Crea un nuevo commit con los cambios con el comando

```bash
  git commit -m "Actualizar sitio web"
```
-  Paso 7. Sube los cambios a tu rama principal (main) en GitHub con el comando

```bash
  git push origin main
```

-  Paso 8. Actualiza la rama gh-pages con los cambios de la rama principal (main) con el comando

```bash
  git subtree push --prefix dist origin gh-pages
```

Al realizar el paso 8. el proyecto se configurara automaticamente a la rama gh-pages

>[!IMPORTANT]
>Por ultimo solo debes activar el enlace, Debes presionar la ⚙️(tuerca) de configuraciones en ABOUT y luego seleccionar con el checklist "Use your GitHub Pages website"

Esto te generara el enlace https://jcarvajallab.github.io/gitpagepruebafinal3/
<br/>
<br/>

## AHORA VAMOS A ACTUALIZAR LA PAGINA WEB GENERADA POR GITHUB PAGES, de ejemplo le agregaremos el VUETIFY

-  Paso 1. Agregaremos el comando para agregar el vuetify al proyecto

```bash
  vue add vuetify
```

-  Paso 2. Nos preguntara si quiermos realizar esta actualizacion y le ponemos si (y/n)

```bash
   y
```
Lo puedes agregar 2 veces si es necesario, algunass veces lanza una alerta

-  Paso 3. Debemos seleccionar la version que corresponda, en mi caso al estar trabajando con VUE 3 debo seleccionar(Esto es a la fecha de 17/12/2024)

```bash
  vuetify 3 - Vue Cli (preview)
```
>[!IMPORTANT]
>SI EL PROYECTO FUE CREADO CON VUE 2 DEBES SELECCIONAR "vuetify 2 - Vue CLI (Recommended)"

-  Paso 5. Validamos que este actualizada la pagina principal con el comando 

```bash
  npm run serve
```

## PASOS PARA ACTUALIZAR LA PAGINA WEB GENERADA POR GITHUB PAGES

Paso 1: Ejecuta el comando npm run build para compilar y generar los archivos de producción en la carpeta dist.

```bash
  npm run build
```

Paso 2: Agregar y commit los cambios

Ejecuta el comando git add dist -f para agregar la carpeta dist al área de preparación (staging area) de Git.
```bash
  git add dist -f
```

Ejecuta el comando git commit -m "Actualizar sitio web" para crear un nuevo commit con los cambios.

```bash
  git commit -m "Se agregan actualizaciones"
```

Paso 3: Subir los cambios a GitHub Pages

Ejecuta el comando git subtree push --prefix dist origin gh-pages para subir los archivos de producción a GitHub Pages.

```bash
  git subtree push --prefix dist origin gh-pages
```

>[!NOTE]
> Al realizar la actualizacion de la web esto provocara que en los archivos GITHUB solo se actualicen los de la rama gh-pages, por lo cual debes seguir el procedimiento normal para actualizar la rama main 

## Subir modificaciones a la rama main

-  Paso 1. Este comando agrega todos los cambios que has hecho en los archivos de tu proyecto al área de preparación

```bash
  git add .
```

-  Paso 2. Este comando guarda los cambios que has preparado y se agrega una nota

```bash
   git commit -m "se modifica proyecto"
```

-  Paso 3. Envía tus cambios guardados en tu repositorio local a un repositorio remoto (como GitHub)

```bash
   git push -u origin main
```

>[!NOTE]
> Si por alguna casualidad se realiza una modificacion en el github de manera en linea(Editando el readme) debes utilizar el comando para que se sincronicen el repositorio local con el enlinea

```bash
  git pull origin main
```
#### Al realizar esto te permitira subir los archivos de forma normal
#### El proyecto se actualizara en la rama main como siempre
