# gitpagepruebafinal3
PASOS PARA AGREGAR UN PROYECTO VUE Y SUBIRLO A GITHUB PAGE

Paso 1. Crear proyecto de VUE CLI (Agregar vuex/router si es necesario)
Paso 2. Crear el repositorio en GitHub y sincronizarlo con el proyecto local
Paso 3. Agregar la siguiente linea de comando a vue.config.js (El proyecto actual es VUE 3)

module.exports = defineConfig({
  transpileDependencies: true,
  publicPath: process.env.NODE_ENV === 'production' ? '/gitpagepruebafinal3/' : '/'
})


Debemos modificar la ruta y agregar la carpeta del proyecto
Paso 4. Luego de haber realizado lo mencionado debemos agrear el siguiente comando a la terminal
**  npm run build
Esto creara la carpeta "dist" con el proyecto actualizado (Basicamente compila el proyecto y lo sube en una carpeta)
Paso 5.Agrega los archivos generados en la carpeta dist al área de preparación (staging area) de Git con el comando 
**  git add dist -f (Lo puedes agregar 2 veces si es necesario, algunass veces lanza una alerta)
Paso 6. Crea un nuevo commit con los cambios con el comando 
**  git commit -m "Actualizar sitio web"
Paso 7.Sube los cambios a tu rama principal (main) en GitHub con el comando 
git push origin main
Paso 8. Actualiza la rama gh-pages con los cambios de la rama principal (main) con el comando 
git subtree push --prefix dist origin gh-pages

Al realizar el paso 8. el proyecto se configurara automaticamente a la rama gh-pages, por ultimo solo debes activar el enlace
Debes presionar la tuerca de configuraciones en ABOUT y luego seleccionar con el checklist Use your GitHub Pages website

Esto te generara el enlace https://jcarvajallab.github.io/gitpagepruebafinal3/
