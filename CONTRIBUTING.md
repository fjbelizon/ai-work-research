# Guía de contribución

Gracias por contribuir a `ai-work-research`.

## Política de ramas

- La rama principal de este repositorio es `main`.
- No se permiten commits ni pushes directos a `main`.
- Si en el futuro se crea o utiliza una rama `master`, aplicará exactamente la misma regla: tampoco se permiten commits ni pushes directos.
- Todo cambio debe realizarse en una rama separada creada a partir de la rama principal.

## Requisito de issue previo

Toda contribución debe estar vinculada a un issue registrado en este repositorio.

- Antes de crear cualquier rama o iniciar cualquier trabajo, comprueba si ya existe un issue que cubra el cambio que deseas hacer.
- Si no existe, crea el issue primero y espera a que sea aceptado/asignado antes de comenzar.
- No se aceptarán ramas de trabajo ni pull requests que no estén vinculados a un issue.
- El nombre de la rama debe incluir el número de issue (por ejemplo, `feature/42-description` o `fix/7-typo`).

## Flujo obligatorio de contribución

1. Abre o identifica el issue que justifica el cambio.
2. Crea una rama para tu trabajo con el número de issue incluido (`feature/<número>-descripción`, `fix/<número>-descripción`, `docs/<número>-descripción`, etc.).
3. Realiza tus cambios en esa rama.
4. Usa commits claros y específicos, con un alcance fácil de revisar.
5. Abre un Pull Request vinculado al issue (usa `Closes #<número>` o `Fixes #<número>` en la descripción).
6. Espera la revisión antes de fusionar.

## Requisitos para cada Pull Request

Cada Pull Request debe incluir:

- referencia explícita al issue que lo justifica (usa `Closes #<número>` o `Fixes #<número>` en la descripción),
- una descripción clara del cambio,
- la motivación o el problema que resuelve (habitualmente cubierta por el propio issue),
- las validaciones realizadas (por ejemplo, revisión manual, pruebas o verificaciones aplicables),
- confirmación de que se siguieron estas directrices.

No se fusionará ninguna PR sin un issue vinculado.

## Buenas prácticas de colaboración

- Mantén los commits claros, pequeños y fáciles de revisar.
- Revisa tu propio cambio antes de solicitar revisión.
- Evita mezclar cambios no relacionados en la misma PR.
- Responde a los comentarios de revisión y ajusta la PR cuando sea necesario.
- Procura mantener una comunicación clara sobre el alcance y el impacto del cambio.

## Ayudas locales y protección real de ramas

Este repositorio incluye un hook versionado en `.githooks/pre-push` que ayuda a detectar intentos de push directo a `main` o `master` desde tu entorno local.

Para habilitarlo en tu clon local:

```bash
git config core.hooksPath .githooks
```

Importante:

- este hook es una ayuda local y no sustituye la protección real de ramas,
- la prevención efectiva de commits o pushes directos debe configurarse en GitHub,
- configura esa protección en **GitHub Settings → Rules → Rulesets** o en **Branch protection rules** para `main` y también para `master` si esa rama llega a crearse.
