# Workflow de despliegue en GitHub

Este repositorio demuestra un workflow de CI/CD utilizando GitHub Actions para desplegar automáticamente un sitio web simple en GitHub Pages.

## Propósito

Este es un ejercicio práctico para entender los principios de CI/CD con las herramientas integradas de GitHub. El workflow despliega automáticamente el sitio web cada vez que se realizan cambios en el archivo `index.html` a través de pull requests a la rama principal.

## Cómo Funciona

1. La rama principal está protegida y requiere pull requests para cualquier cambio
2. Cuando alguien envía un PR que modifica `index.html`, el workflow se ejecuta para verificar la compilación
3. Una vez que el PR es aprobado y fusionado, el workflow despliega automáticamente el sitio actualizado en GitHub Pages

## Para probar el proceso de CI/CD:

1. Clona este repositorio
2. Crea una nueva rama con tu nombre (por ejemplo: `pablo`)
3. Agrega tu nombre a la lista de desarrolladores en `index.html`
4. Confirma los cambios y fusionalos a la rama `staging`
5. Haz un push de los cambios en `staging` para sincronizarlos a GitHub
6. Envía un pull request a la rama principal
7. Una vez aprobado y fusionado, tu nombre aparecerá en el sitio en vivo

## Detalles del workflow

El despliegue es administrado por un workflow de GitHub Actions definido en `.github/workflows/deploy.yml`. El workflow:

- Se activa solo cuando se realizan cambios en `index.html`
- Compila y prepara el sitio durante el proceso de revisión del PR
- Despliega a GitHub Pages solo después de que los cambios se fusionan a la rama principal

## Demostración en Vivo

El sitio web desplegado está disponible en: https://pmedinadev.github.io/gh-deployment-workflow/