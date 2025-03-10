# Workflow de despliegue en GitHub

Este repositorio demuestra un workflow de CI/CD utilizando [GitHub Actions](https://github.com/features/actions) para desplegar automáticamente un sitio web simple en [GitHub Pages](https://pages.github.com/).

## Propósito

Este es un ejercicio práctico para entender los principios de CI/CD con las herramientas integradas de GitHub. El workflow despliega automáticamente el sitio web cada vez que se realizan cambios en el archivo [`index.html`](index.html) a través de pull requests a la rama principal.

## Cómo Funciona

1. La rama principal está protegida y requiere pull requests para cualquier cambio
2. Cuando alguien envía un PR que modifica `index.html`, el workflow se ejecuta para verificar la compilación
3. Una vez que el PR es aprobado y fusionado, el workflow despliega automáticamente el sitio actualizado en GitHub Pages

## Para probar el proceso de CI/CD

1. Clona este repositorio:
```
git clone https://github.com/pmedinadev/gh-deployment-workflow.git
```
2. Crea una nueva rama con tu nombre (por ejemplo: `pablo`):
```
git checkout -b pablo
```
3. Agrega tu nombre a la lista de desarrolladores en `index.html`:
```html
<h5>Developers:</h5>
<ul>
  <li>Jesús Pablo Medina García</li>
  <!-- Agrega aquí tu nombre -->
</ul>
```
4. Confirma los cambios:
```
git add index.html
git commit -m "Update: Nuevo desarrollador agregado"
```
5. Cámbiate a la rama `staging` y fusiona los cambios de tu rama:
```
git checkout -b staging origin/staging
git merge pablo
```
6. Sincroniza tu rama `staging` con la rama remota en GitHub:
```
git push
```
7. Crea un [**pull request**](https://github.com/pmedinadev/gh-deployment-workflow/pulls) para solicitar la fusión de los cambios de la rama `staging` a `main`
8. Una vez aprobado y fusionado, tu nombre aparecerá en el [sitio en vivo](https://pmedinadev.github.io/gh-deployment-workflow/)

## Detalles del workflow

El despliegue es administrado por un workflow de GitHub Actions definido en el archivo [`deploy.yml`](.github/workflows/deploy.yml). El workflow:

- Se activa solo cuando se realizan cambios en `index.html`
- Compila y prepara el sitio durante el proceso de revisión del PR
- Despliega a GitHub Pages solo después de que los cambios se fusionan a la rama principal

## Demostración en Vivo

El sitio web desplegado está disponible en: https://pmedinadev.github.io/gh-deployment-workflow/
