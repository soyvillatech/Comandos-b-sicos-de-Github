# 📘 Guía Completa de Git

> Sistema de control de versiones distribuido para registrar cambios, colaborar en equipo y gestionar el historial de tus proyectos.

<div align="center">

![Excel](https://img.shields.io/badge/Excel-217346?style=flat-square&logo=microsoft-excel&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat-square&logo=python&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat-square&logo=powerbi&logoColor=black)

![Estado](https://img.shields.io/badge/Estado-Completado-brightgreen?style=flat-square)
![Tipo](https://img.shields.io/badge/Tipo-Proyecto_Personal-blueviolet?style=flat-square)
![Licencia](https://img.shields.io/badge/Licencia-Educativo-orange?style=flat-square)

</div>

---

## 🧭 Índice

- [¿Qué es Git?](#-qué-es-git)
- [Configuración inicial](#-configuración-inicial)
- [Crear repositorio](#-crear-repositorio)
- [Estado y seguimiento](#-estado-y-seguimiento)
- [Guardar cambios](#-guardar-cambios)
- [Historial de commits](#-historial-de-commits)
- [Ramas (Branches)](#-ramas-branches)
- [Fusión (Merge)](#-fusión-merge)
- [Rebase](#-rebase)
- [Repositorios remotos](#-repositorios-remotos)
- [Etiquetas (Tags)](#-etiquetas-tags)
- [Stash](#-stash-guardar-cambios-temporales)
- [Deshacer cambios](#-deshacer-cambios)
- [Diferencias entre archivos](#-diferencias-entre-archivos)
- [Alias útiles](#-alias-útiles)
- [Limpieza](#-limpieza)
- [.gitignore](#-gitignore)
- [Buenas prácticas](#-buenas-prácticas)
- [Recursos útiles](#-recursos-útiles)

---

## 🚀 ¿Qué es Git?

Git es un sistema de control de versiones distribuido que te permite:

- 📝 Registrar el historial de cambios de tus archivos
- 👥 Colaborar con otros desarrolladores
- 🔀 Trabajar en paralelo con ramas
- ⏪ Revertir a versiones anteriores en cualquier momento

---

## ⚙️ Configuración inicial

> Configura tu identidad antes de comenzar a usar Git. Esto se aplica a todos tus repositorios.

```bash
# 👤 Configurar nombre de usuario
git config --global user.name "Tu Nombre"

# 📧 Configurar correo electrónico
git config --global user.email "tu@email.com"

# 🎨 Configurar editor de texto predeterminado (ej: VS Code)
git config --global core.editor "code --wait"

# 🌿 Configurar nombre de la rama principal por defecto
git config --global init.defaultBranch main

# 📋 Ver toda la configuración actual
git config --list

# 🔍 Ver un valor específico
git config user.name
```

---

## 📁 Crear repositorio

```bash
# 🆕 Inicializar un repositorio nuevo en la carpeta actual
git init

# 📂 Inicializar con un nombre de carpeta específico
git init nombre-proyecto

# 🌐 Clonar un repositorio existente
git clone <url-del-repositorio>

# 📁 Clonar en una carpeta con nombre personalizado
git clone <url-del-repositorio> nombre-carpeta

# 🔬 Clonar solo la rama más reciente (más rápido)
git clone --depth 1 <url-del-repositorio>
```

---

## 📌 Estado y seguimiento

```bash
# 📊 Ver estado actual de los archivos (modificados, staged, sin seguimiento)
git status

# 📊 Ver estado en formato resumido
git status -s

# ➕ Agregar un archivo específico al área de staging
git add archivo.txt

# ➕ Agregar todos los archivos modificados y nuevos
git add .

# ➕ Agregar solo archivos ya rastreados (ignorar nuevos)
git add -u

# ➕ Agregar archivos de forma interactiva (seleccionar cambios)
git add -p

# ❌ Quitar un archivo del staging (sin perder los cambios)
git restore --staged archivo.txt
```

---

## 💾 Guardar cambios (Commits)

```bash
# 💾 Crear un commit con mensaje
git commit -m "Mensaje descriptivo del commit"

# 💾 Agregar todos los archivos rastreados y hacer commit en un paso
git commit -am "Mensaje del commit"

# ✏️ Modificar el último commit (mensaje o archivos)
git commit --amend -m "Nuevo mensaje corregido"

# 📭 Hacer un commit vacío (útil para disparar CI/CD)
git commit --allow-empty -m "trigger deploy"

# 📅 Hacer un commit con fecha personalizada
git commit -m "Mensaje" --date="2024-01-01T12:00:00"
```

---

## 🔍 Historial de commits

```bash
# 📜 Ver historial completo
git log

# 📄 Ver historial resumido (una línea por commit)
git log --oneline

# 🌳 Ver historial con gráfico de ramas
git log --oneline --graph --all

# 👤 Ver commits de un autor específico
git log --author="Nombre"

# 📅 Ver commits en un rango de fechas
git log --after="2024-01-01" --before="2024-12-31"

# 🔎 Buscar commits por mensaje
git log --grep="palabra clave"

# 📂 Ver historial de un archivo específico
git log -- archivo.txt

# 🔢 Ver solo los últimos N commits
git log -5

# 📊 Ver estadísticas de cambios por commit
git log --stat

# 🎨 Formato personalizado del log
git log --pretty=format:"%h - %an, %ar : %s"
```

---

## 🌿 Ramas (Branches)

```bash
# 📋 Ver ramas locales
git branch

# 🌐 Ver ramas remotas
git branch -r

# 🌍 Ver todas las ramas (locales y remotas)
git branch -a

# 🆕 Crear una rama nueva
git branch nombre-rama

# 🔄 Cambiar a una rama existente
git checkout nombre-rama

# ✨ Cambiar de rama (forma moderna)
git switch nombre-rama

# 🆕 Crear y cambiar a una nueva rama
git checkout -b nombre-rama

# 🆕 Crear y cambiar (forma moderna)
git switch -c nombre-rama

# 🔄 Renombrar la rama actual
git branch -m nuevo-nombre

# 🗑️ Eliminar una rama (solo si ya fue fusionada)
git branch -d nombre-rama

# 🗑️ Eliminar una rama forzosamente
git branch -D nombre-rama

# 🗑️ Eliminar una rama remota
git push origin --delete nombre-rama

# 🔍 Ver qué rama contiene cierto commit
git branch --contains <hash-commit>
```

---

## 🔀 Fusión (Merge)

```bash
# 🔀 Fusionar una rama con la rama actual
git merge nombre-rama

# 📌 Fusionar sin fast-forward (mantiene historial de ramas)
git merge --no-ff nombre-rama

# ✉️ Fusionar con mensaje de commit personalizado
git merge --no-ff nombre-rama -m "Fusión de nombre-rama"

# ❌ Cancelar un merge en conflicto
git merge --abort

# 🍒 Traer un commit específico de otra rama (cherry-pick)
git cherry-pick <hash-commit>
```

---

## 🔁 Rebase

> ⚠️ Usar con cuidado en ramas compartidas, ya que reescribe el historial.

```bash
# 🔁 Reorganizar commits sobre otra rama
git rebase main

# 🎛️ Rebase interactivo (editar, unir, reordenar commits)
git rebase -i HEAD~3

# ❌ Cancelar un rebase en curso
git rebase --abort

# ✅ Continuar rebase tras resolver conflictos
git rebase --continue
```

---

## 🌐 Repositorios remotos

```bash
# 🔗 Agregar un repositorio remoto
git remote add origin <url>

# 📋 Ver repositorios remotos configurados
git remote -v

# ✏️ Cambiar la URL de un remoto
git remote set-url origin <nueva-url>

# ❌ Eliminar un remoto
git remote remove origin

# 📤 Enviar cambios al repositorio remoto
git push origin main

# 📤 Subir una rama nueva y establecerla como seguimiento
git push -u origin nombre-rama

# 📤 Forzar el push (⚠️ reescribe el remoto)
git push --force

# 📥 Obtener y fusionar cambios del remoto
git pull

# 📥 Obtener cambios sin fusionar (solo descarga)
git fetch

# 📥 Obtener cambios de todos los remotos
git fetch --all

# 🔄 Actualizar referencias remotas locales
git remote update
```

---

## 🏷️ Etiquetas (Tags)

> Las etiquetas se usan para marcar versiones o hitos importantes del proyecto.

```bash
# 🏷️ Crear una etiqueta ligera
git tag v1.0.0

# 🏷️ Crear una etiqueta anotada (con mensaje y autor)
git tag -a v1.0.0 -m "Versión 1.0.0 estable"

# 📋 Ver todas las etiquetas
git tag

# 🔍 Ver detalles de una etiqueta
git show v1.0.0

# 📤 Enviar una etiqueta al remoto
git push origin v1.0.0

# 📤 Enviar todas las etiquetas al remoto
git push origin --tags

# 🗑️ Eliminar una etiqueta local
git tag -d v1.0.0

# 🗑️ Eliminar una etiqueta del remoto
git push origin --delete v1.0.0
```

---

## 🗄️ Stash (Guardar cambios temporales)

> Guarda cambios sin hacer commit, útil para cambiar de contexto rápidamente.

```bash
# 📦 Guardar cambios actuales en el stash
git stash

# 📦 Guardar con un nombre descriptivo
git stash save "descripción de mis cambios"

# 📋 Ver todos los stashes guardados
git stash list

# 🔄 Aplicar el stash más reciente (sin eliminarlo)
git stash apply

# 🔄 Aplicar y eliminar el stash más reciente
git stash pop

# 🔄 Aplicar un stash específico
git stash apply stash@{2}

# 🗑️ Eliminar un stash específico
git stash drop stash@{1}

# 🗑️ Eliminar todos los stashes
git stash clear

# 🌿 Crear una rama desde un stash
git stash branch nueva-rama stash@{0}
```

---

## ⏪ Deshacer cambios

```bash
# ↩️ Descartar cambios en un archivo (no staged)
git restore archivo.txt

# ↩️ Descartar todos los cambios no staged
git restore .

# 🔙 Quitar archivo del área de staging
git restore --staged archivo.txt

# ↩️ Revertir un commit (crea un nuevo commit que deshace)
git revert <hash-commit>

# 🔙 Deshacer el último commit manteniendo los cambios (staged)
git reset --soft HEAD~1

# 🔙 Deshacer el último commit y dejar cambios sin staged
git reset --mixed HEAD~1

# ⚠️ Deshacer el último commit ELIMINANDO los cambios permanentemente
git reset --hard HEAD~1

# ⚠️ Deshacer N commits y eliminar todos los cambios
git reset --hard HEAD~3

# 🕵️ Recuperar un archivo de un commit anterior
git checkout <hash-commit> -- archivo.txt
```

---

## 🔎 Diferencias entre archivos

```bash
# 📊 Ver cambios no staged (área de trabajo vs staging)
git diff

# 📊 Ver cambios staged (staging vs último commit)
git diff --staged

# 📊 Ver diferencias entre dos ramas
git diff main nombre-rama

# 📊 Ver diferencias entre dos commits
git diff <hash1> <hash2>

# 📊 Ver qué archivos cambiaron entre commits
git diff --name-only <hash1> <hash2>

# 📊 Ver diferencias de un archivo específico
git diff archivo.txt
```

---

## 🔗 Alias útiles

> Crea atajos para los comandos que usas con más frecuencia.

```bash
# ⚡ Historial visual compacto
git config --global alias.lg "log --oneline --graph --all --decorate"

# ⚡ Estado resumido
git config --global alias.st "status -s"

# ⚡ Agregar todo y hacer commit rápido
git config --global alias.ac "!git add . && git commit -m"

# ⚡ Deshacer último commit sin perder cambios
git config --global alias.undo "reset --soft HEAD~1"

# Usarlos:
git lg
git st
git undo
```

---

## 🧹 Limpieza

```bash
# 🗑️ Ver qué archivos no rastreados se eliminarían (simulación)
git clean -n

# 🗑️ Eliminar archivos no rastreados
git clean -f

# 🗑️ Eliminar archivos y carpetas no rastreados
git clean -fd

# 🗑️ Eliminar archivos ignorados y no rastreados
git clean -fdx
```

---

## 🚫 .gitignore

> El archivo `.gitignore` le indica a Git qué archivos o carpetas debe ignorar.

```bash
# Crear archivo .gitignore
touch .gitignore
```

Ejemplo de contenido para un proyecto Node.js:

```
# 📦 Dependencias
node_modules/

# 🔐 Variables de entorno
.env
.env.local

# 🏗️ Build
dist/
build/

# 🖥️ Sistema operativo
.DS_Store
Thumbs.db

# 🛠️ IDEs
.vscode/
.idea/
```

```bash
# 📋 Ver archivos ignorados
git ls-files --ignored --exclude-standard

# 🗑️ Dejar de rastrear un archivo ya commiteado (sin eliminarlo)
git rm --cached archivo.txt

# 🗑️ Dejar de rastrear una carpeta ya commiteada
git rm -r --cached carpeta/
```

---

## ✅ Buenas prácticas

| 📌 Práctica | 💡 Descripción |
|------------|----------------|
| ✍️ Mensajes claros | Escribe commits descriptivos: `feat: agrega formulario de login` |
| 🔬 Commits pequeños | Un commit por cambio lógico, no acumules muchos cambios |
| 🌿 Usar ramas | Una rama por funcionalidad, bug o experimento |
| 🔄 Sincronizar | Haz `git pull` antes de empezar a trabajar |
| 🚫 No forzar | Evita `git push --force` en ramas compartidas |
| 🏷️ Versionar | Usa tags para marcar versiones de producción (`v1.0.0`) |
| 📝 .gitignore | Configúralo desde el inicio del proyecto |

### 📝 Convención de mensajes de commit

> 📌 Los mensajes deben escribirse en **imperativo (presente)**  
> Ejemplo: *"agregar"*, *"corregir"*, *"actualizar"* (NO en pasado)

---

### 📊 Tipos de commit según rol

| Tipo      | Programador 💻                  | Analista de Datos 📊              | Data Scientist 🤖                | Descripción general |
|----------|--------------------------------|----------------------------------|----------------------------------|---------------------|
| feat     | agregar funcionalidad           | agregar análisis o reporte        | agregar modelo o experimento      | Introduce algo nuevo |
| fix      | corregir bug                   | corregir cálculos o queries       | corregir datos o modelo           | Soluciona errores    |
| docs     | documentar código              | documentar análisis               | documentar modelos               | Solo documentación   |
| style    | aplicar formato                | limpiar notebook                 | formatear código sin lógica       | Cambios visuales     |
| refactor | mejorar código                 | optimizar consultas               | mejorar pipeline/modelo           | Sin cambiar resultado |
| test     | agregar tests                  | validar datos                     | evaluar modelos                  | Pruebas              |
| chore    | actualizar dependencias        | actualizar datasets               | mantenimiento general             | Tareas menores       |

---

### ➕ Tipos adicionales

| Tipo      | Uso principal | Ejemplo |
|----------|--------------|--------|
| perf     | mejorar rendimiento | perf: optimizar consulta SQL |
| build    | dependencias / build | build: actualizar versión de pandas |
| ci       | integración continua | ci: agregar workflow de deploy |
| revert   | revertir cambios | revert: eliminar cambio en modelo |
| data     | cambios en datos | data: actualizar dataset de ventas |
| exp      | experimentos | exp: probar modelo random forest |
| config   | configuración | config: agregar variables de entorno |
| security | seguridad | security: proteger credenciales |

---

### ✅ Ejemplos correctos

    feat: agregar dashboard de ventas
    fix: corregir cálculo de ingresos
    docs: actualizar documentación del proyecto
    refactor: simplificar lógica de usuarios
    test: agregar pruebas para API
    perf: optimizar consulta SQL
    data: actualizar dataset de clientes
    exp: probar modelo XGBoost

---

### ❌ Ejemplos incorrectos

    feat: agregué dashboard ❌
    fix: error arreglado ❌
    docs: cambios ❌

---

### 🔥 Buenas prácticas

- Usar verbo en **imperativo** (agregar, corregir, actualizar…)
- No usar punto final
- Mantener el mensaje corto (~50 caracteres)
- Ser claro y específico
- Usar minúsculas después de `:`

---

💡 Ejemplo mental:
> "Este commit **agrega** una funcionalidad" ✔️


## 📚 Recursos útiles

| 🔗 Recurso | 📄 Descripción |
|-----------|----------------|
| [Documentación oficial](https://git-scm.com/docs) | Referencia completa de todos los comandos |
| [Pro Git Book](https://git-scm.com/book/es/v2) | Libro oficial gratuito en español |
| [Learn Git Branching](https://learngitbranching.js.org/) | Tutorial interactivo visual |
| [Oh My Git!](https://ohmygit.org/) | Juego para aprender Git |
| [Conventional Commits](https://www.conventionalcommits.org/es/) | Estándar para mensajes de commit |
| [gitignore.io](https://www.toptal.com/developers/gitignore) | Generador de .gitignore por lenguaje |

---

## 🗺️ Flujo de trabajo básico

```
📁 Working Directory  →  git add  →  📦 Staging Area  →  git commit  →  🏠 Local Repo
                                                                              ↓
                                                                         git push
                                                                              ↓
                                                                        🌐 Remote Repo
```

---

## 👤 Autor

<div align="center">

### Brayan Villanueva
**Data Analyst | Excel · Python · SQL · Power BI**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-soyvillatech-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/soyvillatech)
[![GitHub](https://img.shields.io/badge/GitHub-soyvillatech-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/soyvillatech)
[![Instagram](https://img.shields.io/badge/Instagram-soyvillatech-E4405F?style=flat-square&logo=instagram&logoColor=white)](https://instagram.com/soyvillatech)
[![Facebook](https://img.shields.io/badge/Facebook-soyvillatech-1877F2?style=flat-square&logo=facebook&logoColor=white)](https://facebook.com/soyvillatech)

**Comunidad PracTeam**

[![Facebook](https://img.shields.io/badge/Facebook-practeam-1877F2?style=flat-square&logo=facebook&logoColor=white)](https://facebook.com/practeam)
[![Instagram](https://img.shields.io/badge/Instagram-prac__team-E4405F?style=flat-square&logo=instagram&logoColor=white)](https://instagram.com/prac_team)
[![TikTok](https://img.shields.io/badge/TikTok-@practeam-000000?style=flat-square&logo=tiktok&logoColor=white)](https://tiktok.com/@practeam)
[![Threads](https://img.shields.io/badge/Threads-@prac__team-000000?style=flat-square&logo=threads&logoColor=white)](https://threads.net/@prac_team)
[![YouTube](https://img.shields.io/badge/YouTube-practeam-FF0000?style=flat-square&logo=youtube&logoColor=white)](https://youtube.com/@practeam)

</div>

---

## 📄 Licencia

```
Proyecto de uso educativo y demostrativo.
Se permite el uso total del material para practicar y mejorar tus habilidades.
```

> ⭐ Si este proyecto te fue útil, ¡dale una estrella en GitHub! Ayuda a que más personas lo encuentren.