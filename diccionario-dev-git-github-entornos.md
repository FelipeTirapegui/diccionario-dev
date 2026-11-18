# Diccionario Dev — Git, GitHub y Entornos

Guia rapida de los terminos que usamos en el dia a dia con Git, GitHub y los distintos entornos de un proyecto, para tener a mano cuando aparezca una palabra nueva en una conversacion tecnica.

## Orden tipico: que se hace primero?

Asi se levanta un proyecto desde cero y asi se trabaja despues, dia a dia, sobre lo ya levantado.

1. Clonar el repositorio (`git clone <url>`): trae una copia completa del codigo y su historial a tu computador.
2. Entrar a la carpeta del proyecto y revisar el README: ahi suele estar que version de Node, Python u otra herramienta se necesita.
3. Instalar las dependencias (`npm install`, `pip install -r requirements.txt`, etc.): descarga las librerias que el codigo necesita para correr.
4. Configurar las variables de entorno (archivo `.env`): claves, URLs de base de datos u otros valores que no van en el codigo. Normalmente se piden a alguien que ya tenga el proyecto corriendo.
5. Levantar el proyecto en modo desarrollo ("correr en dev", `npm run dev` o equivalente): queda funcionando en tu computador (`localhost`), mostrando los cambios al vuelo mientras programas.
6. Crear una rama (branch) propia desde `main` (o `develop`) para la tarea en la que vas a trabajar, sin tocar directamente la rama principal.
7. Programar y probar los cambios en dev, guardando el avance en commits.
8. Subir la rama al repositorio remoto (push) para que quede disponible en GitHub.
9. Abrir un Pull Request (PR) para que el equipo revise el codigo antes de integrarlo.
10. Una vez aprobado, se hace merge de la rama a la principal.
11. El codigo pasa por CI/CD (build + tests automaticos) y se despliega (deploy) al entorno que corresponda: primero test o staging, y al final produccion (prod).

En resumen: primero se levanta el proyecto en local (clonar, instalar, correr en dev) y recien despues entra el flujo de trabajo en equipo (branch, commit, push, PR, merge, deploy).

## Control de versiones basico

| Termino | Que es |
| --- | --- |
| Repo / repositorio | La carpeta del proyecto con todo su codigo e historial de cambios. |
| Clone | Descargar una copia completa de un repositorio remoto a tu computador. |
| Commit | Un "guardado" con un mensaje que describe los cambios hechos hasta ese punto. |
| Branch (rama) | Una linea de trabajo independiente para desarrollar algo sin afectar el codigo principal. |
| Push | Subir tus commits locales al repositorio remoto (GitHub). |
| Pull | Traer a tu computador los cambios que otros subieron al remoto. |
| Merge | Juntar los cambios de una rama dentro de otra (por ejemplo, de tu branch a main). |
| Remote | La version del repositorio que vive en un servidor (GitHub), no en tu computador. |
| Origin | El nombre por defecto que Git le da al repositorio remoto del que clonaste. |
| Main / master | La rama principal del proyecto, la que normalmente refleja el codigo "oficial". |
| Status | Muestra que archivos cambiaste y si estan listos para commitear. |
| Stash | Guarda cambios a medio hacer sin commitearlos, para recuperarlos mas tarde. |

## Flujo de trabajo colaborativo

| Termino | Que es |
| --- | --- |
| Fork | Una copia propia de un repositorio ajeno, en tu cuenta, para proponer cambios sin tocar el original. |
| Pull Request (PR) | Una solicitud para integrar los cambios de una rama a otra, revisada por el equipo antes de aprobarla. |
| Code review | La revision que hace otra persona del codigo de un PR antes de aprobarlo. |
| Merge conflict | Cuando Git no puede combinar automaticamente los cambios de dos ramas porque tocaron las mismas lineas; hay que resolverlo a mano. |
| Rebase | Reordenar los commits de una rama para que parezca que se crearon sobre la version mas reciente de main, dejando un historial mas limpio. |
| Squash | Juntar varios commits en uno solo, normalmente al integrar un PR. |
| Tag / release | Una marca sobre un commit especifico que identifica una version publicada del proyecto (ej: v1.2.0). |

## Entornos

| Termino | Que es |
| --- | --- |
| Dev (desarrollo) | El entorno donde se programa y se prueba en el momento; normalmente corre en tu propio computador. |
| "Correr en dev" / run dev | Levantar el proyecto en modo desarrollo (ej: `npm run dev`), con recarga automatica al guardar cambios. |
| Localhost | Tu propio computador visto como servidor; una direccion tipo `localhost:3000` solo es accesible desde tu maquina. |
| Test / QA | Entorno donde se prueban los cambios de forma mas formal antes de pasarlos a produccion, a veces con datos de prueba. |
| Staging | Una replica casi identica a produccion, usada como ultimo chequeo antes del deploy final. |
| Prod (produccion) | El entorno real que usan los clientes; los cambios aqui afectan directamente el servicio en vivo. |
| Variables de entorno (.env) | Valores de configuracion (claves, URLs, credenciales) que cambian segun el entorno y no se escriben directo en el codigo. |

## Build y despliegue

| Termino | Que es |
| --- | --- |
| Build | Compilar u optimizar el codigo fuente para dejarlo listo para ejecutarse en un entorno real (distinto de correrlo en dev). |
| Deploy (desplegar) | Publicar una nueva version del proyecto en un entorno (test, staging o prod) para que quede disponible ahi. |
| CI/CD | Integracion y entrega continua: procesos automaticos que corren tests y hacen el build/deploy cada vez que se sube codigo. |
| Pipeline | La secuencia de pasos automaticos del CI/CD (build, test, deploy) que corre cada vez que hay un cambio. |
| Release | Una version especifica del proyecto que se publica formalmente, normalmente identificada con un numero (ej: v2.1.0). |
| Rollback | Volver a una version anterior porque la ultima tuvo un problema en el entorno donde se desplegaron los cambios. |
| Hotfix | Una correccion urgente que se despliega directo a produccion para arreglar un problema critico. |
| Versionado semantico (semver) | Convencion de numerar versiones como MAYOR.MENOR.PARCHE (ej: 1.4.2), segun el tipo de cambio hecho. |

## Comandos rapidos (en el orden en que se usan)

| Comando | Que hace |
| --- | --- |
| `git clone <url>` | Descarga el repositorio a tu computador. |
| `npm install` | Instala las dependencias del proyecto. |
| `npm run dev` | Levanta el proyecto en modo desarrollo. |
| `git checkout -b <nombre>` | Crea una rama nueva y te mueves a ella. |
| `git status` | Muestra que archivos cambiaste. |
| `git add .` | Marca los cambios para el proximo commit. |
| `git commit -m "mensaje"` | Guarda los cambios marcados con un mensaje descriptivo. |
| `git push` | Sube tu rama al repositorio remoto. |
| `git pull` | Trae los cambios mas recientes del remoto. |
| `git merge <rama>` | Integra los cambios de otra rama a la actual. |
