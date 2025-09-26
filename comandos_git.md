# 📝 Chuleta Completa Git

## Índice

1. [Buenas Prácticas](#1-buenas-prácticas)
2. [Comandos Básicos Git](#2-comandos-básicos-git)
3. [Comandos Avanzados Git](#3-comandos-avanzados-git)

---

<span style="color:red"></span>


## 1. Buenas Prácticas

| Tema                        | Buenas prácticas                                                                 |
|-----------------------------|----------------------------------------------------------------------------------|
| <span style="color:red">**Mensajes de commit**      | - Usa imperativo: **Add feature**, **Fix bug** (no **Added**)</span>                  |
|                             | - Máx. 50-72 caracteres, corto y descriptivo                                     |
|                             | - Explica el *por qué* en el cuerpo del commit                                   |
|                             | - Evita mensajes genéricos: **update**, **cambios**                             |
| <span style="color:red">**Ramas (branching)**       | - Nombres descriptivos: **feature/login-ui**, **bugfix/api-timeout**</span>           |
|                             | - Flujo claro: **main/master** estable, **develop** en progreso                 |
|                             | - Ramas cortas y específicas (no acumular semanas)                              |
|                             | - Flujos: **GitFlow** (**main + develop + feature/, release/, hotfix/**)       |
|                             |   **GitHub Flow** (ramas cortas desde **main** + PR/MR)                         |
|                             |   **Trunk-Based** (commits pequeños y frecuentes en **main**)                   |
| <span style="color:red">**Commits y pushes** </span>       | - Commits pequeños y frecuentes (un commit = un cambio lógico)                  |
|                             | - Sincroniza con **git pull --rebase** antes de **push**                        |
|                             | - Evita **git push --force** (mejor --force-with-lease)                        |
| <span style="color:red">**Pull Requests / MRs** </span>   | - PR/MR con descripción clara y capturas si aplica                               |
|                             | - Pide revisión de compañeros antes de **merge**                                 |
|                             | - Usa **squash & merge** para historial limpio                                  |
| <span style="color:red">**Etiquetas y versiones** </span>  | - Usa **tags** para releases: **v1.0.0**, **v2.1.3**                             |
|                             | - Sigue **SemVer**: **MAJOR.MINOR.PATCH**                                       |
| <span style="color:red">**Limpieza del repo** </span>       | - Añade **.gitignore** para binarios, logs, dependencias                        |
|                             | - Usa **git clean -f** con cuidado para limpiar basura                          |
|                             | - Revisa **git status** siempre antes de **commit/push**                        |

---

## 2. Comandos Básicos Git

| Comando                                 | Descripción                                                      |
|----------------------------------------|------------------------------------------------------------------|
| **git config --global user.name "Nombre"** | Define el nombre de usuario global                               |
| **git config --global user.email "correo@ejemplo.com"** | Define el correo global                                         |
| **git config --list**                     | Lista configuración actual                                       |
| **git init**                              | Inicializa un nuevo repositorio                                   |
| **git clone <url>**                       | Clona un repositorio remoto                                       |
| **git status**                            | Muestra estado de archivos                                        |
| **git add <archivo>**                     | Añade un archivo al staging                                        |
| **git add .**                             | Añade todos los cambios                                           |
| **git reset <archivo>**                   | Quita un archivo del staging                                      |
| **git diff**                              | Diferencias no preparadas                                         |
| **git diff --staged**                     | Diferencias en staging                                           |
| **git commit -m "mensaje"**               | Crea un commit con mensaje                                        |
| **git commit -am "mensaje"**              | Añade y comitea archivos ya trackeados                            |
| **git log**                               | Historial de commits                                             |
| **git log --oneline**                     | Historial resumido                                               |
| **git show <hash>**                        | Info de un commit específico                                      |
| **git branch**                             | Lista ramas                                                     |
| **git branch <nombre>**                    | Crea nueva rama                                                 |
| **git checkout <rama>**                    | Cambia de rama                                                  |
| **git checkout -b <rama>**                 | Crea y cambia a rama                                            |
| **git switch <rama>**                      | Cambia de rama (moderno)                                        |
| **git switch -c <rama>**                   | Crea y cambia a rama nueva                                       |
| **git merge <rama>**                        | Fusiona rama en la actual                                        |
| **git branch -d <rama>**                   | Elimina rama local                                               |
| **git remote -v**                           | Lista remotos configurados                                       |
| **git remote add origin <url>**             | Añade remoto origin                                             |
| **git fetch**                               | Descarga cambios sin aplicar                                     |
| **git pull**                                | Descarga y fusiona cambios                                       |
| **git push**                                | Sube commits al remoto                                          |
| **git push -u origin <rama>**               | Conecta rama local con remota                                    |
| **git restore <archivo>**                   | Restaura archivo al último commit                                 |
| **git restore --staged <archivo>**         | Quita archivo del staging                                        |
| **git reset --hard <hash>**                | Resetea repo a un commit (**peligroso**)                         |
| **git revert <hash>**                       | Crea commit que revierte otro                                     |
| **git stash**                               | Guarda cambios sin commit                                        |
| **git stash pop**                           | Restaura cambios guardados                                       |
| **git stash list**                          | Lista stashes guardados                                         |
| **git show**                                | Info de commit, tag o archivo                                     |
| **git blame <archivo>**                     | Quién cambió cada línea                                          |
| **git grep <texto>**                        | Busca texto en el repo                                           |
| **git tag**                                 | Lista etiquetas                                                 |
| **git tag <nombre>**                        | Crea etiqueta ligera                                             |
| **git tag -a <nombre> -m "msg"**           | Crea etiqueta anotada                                            |
| **git push origin <tag>**                   | Sube etiqueta al remoto                                          |
| **git rm <archivo>**                        | Elimina archivo del repo y disco                                  |
| **git mv <origen> <destino>**              | Mueve/renombra archivo                                           |
| **git clean -f**                            | Elimina archivos no trackeados                                   |

---

## 3. Comandos Avanzados Git

| Comando                                   | Descripción                                                           |
|------------------------------------------|-----------------------------------------------------------------------|
| **git rebase <rama>**                        | Reaplica commits de la rama actual sobre otra                          |
| **git rebase -i <hash>**                     | Rebase interactivo (editar, reordenar, squash)                         |
| **git cherry-pick <hash>**                   | Aplica un commit específico en la rama actual                           |
| **git reflog**                               | Muestra historial de todas las acciones realizadas                     |
| **git reset --soft <hash>**                  | Vuelve a un commit sin perder cambios en staging                        |
| **git reset --mixed <hash>**                 | Vuelve a un commit manteniendo cambios en directorio                   |
| **git reset --hard <hash>**                  | Vuelve a un commit eliminando cambios (**peligroso**)                   |
| **git remote show origin**                   | Muestra info detallada del remoto                                       |
| **git remote prune origin**                  | Limpia referencias a ramas remotas eliminadas                           |
| **git fetch --all --prune**                  | Descarga y limpia ramas remotas obsoletas                                |
| **git push origin --delete <rama>**          | Elimina una rama remota                                                 |
| **git push --force**                         | Fuerza el push (**sobreescribe historial remoto**)                     |
| **git push --force-with-lease**             | Push forzado más seguro                                                |
| **git submodule add <url>**                  | Añade un submódulo al proyecto                                         |
| **git submodule init**                       | Inicializa submódulos en un repo clonado                                |
| **git submodule update**                     | Actualiza submódulos a su commit correcto                               |
| **git submodule foreach <cmd>**              | Ejecuta un comando en cada submódulo                                    |
| **git tag -d <tag>**                         | Elimina etiqueta local                                                 |
| **git push origin :refs/tags/<tag>**        | Elimina etiqueta remota                                                |
| **git fetch --tags**                         | Descarga todas las etiquetas                                           |
| **git stash save "mensaje"**                 | Guarda stash con mensaje                                              |
| **git stash apply stash@{n}**                | Aplica un stash específico                                             |
| **git stash drop stash@{n}**                 | Elimina un stash específico                                            |
| **git stash clear**                          | Elimina todos los stashes                                              |
| **.git/hooks/pre-commit**                    | Script que se ejecuta antes de un commit                                |
| **.git/hooks/post-merge**                    | Script que se ejecuta tras un merge exitoso                             |
| **git bisect start**                         | Inicia búsqueda binaria de un commit con bug                             |
| **git bisect bad**                           | Marca un commit como defectuoso                                         |
| **git bisect good**                          | Marca un commit como correcto                                           |
| **git archive --format=zip HEAD > repo.zip** | Exporta repo como ZIP                                                  |
| **git shortlog -sn**                          | Lista autores ordenados por número de commits                           |
| **git describe --tags**                       | Describe commit actual con la etiqueta más cercana                      |
