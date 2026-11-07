# Entregable 1 - CI/CD

Primer entregable del curso de CI/CD - 2026.

## Integrantes

- **Jennifer Andrea Lopez Gomez** (`jalopezg4`)
- **Santiago Alexander Cardenas Laverde** (`AIDouglas`)

## Respuestas

### 1. ¿Qué eventos configuraste para disparar tu workflow y por qué?

Configuramos dos eventos:

- **`push` en la rama `main`:** el workflow se ejecuta cada vez que subimos cambios a esa rama.
- **`workflow_dispatch`:** permite ejecutarlo manualmente desde GitHub cuando queramos, sin tener que hacer otro commit.

### 2. ¿Qué sistema operativo utiliza el runner `ubuntu-latest`?

El runner utiliza Ubuntu Linux 24.04.5 LTS. Es como un computador virtual que GitHub pone a disposición para ejecutar el workflow. Por eso funciona aunque nuestro computador sea Windows o macOS, el proceso no se hace en nuestro local.

El shell es el programa que entiende los comandos de `run`. Aca usamos Bash, que se encarga de ejecutar comandos como `echo` y `date`. También aprovechamos ese computador virtual para instalar Python y correr el script.

### 3. Menciona al menos tres acciones prediseñadas del Marketplace

- **`actions/cache`:** guarda archivos que usamos seguido, como las dependencias, para que el workflow corra más rápido y no tenga que descargarlas otra vez.
- **`github/codeql-action`:** le pega una revisada al código para ver si tiene algún problema de seguridad.
- **`docker/login-action`:** nos ayuda a iniciar sesión en Docker Hub u otro registro para subir o bajar imágenes.

### 4. ¿Qué es un secreto en GitHub Actions y para qué se usa?

Un secreto es un dato privado, como una contraseña, un token o una clave de API. Se guarda en GitHub para no ponerlo directamente en el código y evitar que cualquiera lo pueda ver.

En este workflow no usamos secretos. Pero si necesitáramos una contraseña para una API, la guardaríamos en **Secrets and variables**. Así la clave queda protegida y no se muestra ni en el código.

### 5. Reflexiona sobre el uso de GitHub Actions

**Jennifer Andrea Lopez Gomez:** Automatizaría las pruebas y la revisión del código cada vez que se haga un `pull request`. Así encontraríamos errores antes de subir los cambios a `main`.

**Santiago Alexander Cardenas Laverde:** Automatizaría la publicación de la aplicación cuando se apruebe un cambio en `main`. También pondría avisos cuando algo falle para poder corregirlo rápido.

[Ejecución exitosa](https://github.com/jalopezg4/Entregable-1-CICD/actions/runs/42382874911/job/128434015254)
