# Curso: Bash Scripting en Ubuntu Linux 24 LTS
**Duración total:** 16 horas cronológicas
**Modalidad sugerida:** 4 sesiones de 4 horas u 8 sesiones de 2 horas
**Perfil del alumno:** Conocimientos básicos de computación, sin experiencia previa obligatoria en Linux
**Requisitos técnicos:** Un equipo (físico, VM o WSL) con Ubuntu 24.04 LTS instalado, acceso a terminal, editor de texto (nano/vim), conexión a internet para `apt`

---

## Distribución general de horas

| Módulo | Tema | Teoría | Práctica | Total |
|---|---|---|---|---|
| 1 | Introducción a Linux, Ubuntu y la terminal | 0:30 | 0:30 | 1:00 |
| 2 | Sistema de archivos y navegación | 0:30 | 1:00 | 1:30 |
| 3 | Manejo de archivos y directorios | 0:30 | 1:00 | 1:30 |
| 4 | Permisos, usuarios y propietarios | 0:30 | 1:00 | 1:30 |
| 5 | Redirección, tuberías y filtros básicos | 0:30 | 1:00 | 1:30 |
| 6 | Procesamiento de texto (grep, sed, awk, cut, sort) | 0:45 | 1:15 | 2:00 |
| 7 | Variables, comillas y expansión en bash | 0:30 | 0:45 | 1:15 |
| 8 | Estructuras de control (if, case, bucles) | 0:30 | 1:00 | 1:30 |
| 9 | Funciones, parámetros posicionales y scripts | 0:30 | 1:00 | 1:30 |
| 10 | Gestión de procesos y control de trabajos | 0:20 | 0:40 | 1:00 |
| 11 | Gestión de paquetes (APT) y servicios (systemd) | 0:20 | 0:40 | 1:00 |
| 12 | Automatización (cron, at) y buenas prácticas/debugging | 0:20 | 0:40 | 1:00 |
| **Total** | | **5:45** | **10:15** | **16:00** |

---

## Módulo 1 — Introducción a Linux, Ubuntu y la terminal (1:00)

### Teoría (30 min)
- Breve historia de Unix, Linux y distribuciones (Ubuntu, Debian family)
- Qué es una shell y qué es bash; otras shells (sh, zsh, dash)
- Arquitectura básica: kernel, shell, sistema de archivos
- Novedades relevantes de Ubuntu 24.04 LTS (soporte, versión de bash incluida)
- La terminal: emuladores de terminal en Ubuntu (GNOME Terminal), acceso vía SSH

### Práctica (30 min)
- Abrir la terminal, reconocer el prompt (`usuario@host:~$`)
- Comandos iniciales: `whoami`, `hostname`, `uname -a`, `date`, `uptime`
- Uso de `man`, `--help`, `apropos`, `info`
- Historial de comandos: flechas, `history`, `Ctrl+R`

---

## Módulo 2 — Sistema de archivos y navegación (1:30)

### Teoría (30 min)
- Jerarquía estándar de archivos (FHS): `/`, `/home`, `/etc`, `/var`, `/usr`, `/bin`, `/tmp`
- Rutas absolutas y relativas
- Conceptos: directorio actual, directorio home, enlaces simbólicos y duros

### Práctica (1:00)
- `pwd`, `cd`, `ls` (con `-l`, `-a`, `-h`, `-R`)
- Navegación con `.`, `..`, `~`, `-`
- `tree` (instalación con apt si no está)
- Creación de estructura de carpetas de práctica con `mkdir -p`
- Enlaces: `ln` y `ln -s`
- Ejercicio guiado: crear un árbol de directorios simulando un proyecto

---

## Módulo 3 — Manejo de archivos y directorios (1:30)

### Teoría (30 min)
- Comandos de creación, copia, movimiento y borrado
- Comodines (wildcards): `*`, `?`, `[]`
- Visualización de contenido de archivos

### Práctica (1:00)
- `touch`, `cp`, `mv`, `rm` (con `-r`, `-i`, `-f`)
- `cat`, `less`, `more`, `head`, `tail` (incluyendo `tail -f`)
- `file`, `stat`, `wc`
- Editores en terminal: `nano` y fundamentos de `vim` (modo inserción/comando, guardar y salir)
- Ejercicio: descargar/crear varios archivos de texto y aplicar comandos de manipulación masiva con comodines

---

## Módulo 4 — Permisos, usuarios y propietarios (1:30)

### Teoría (30 min)
- Modelo de permisos Unix: lectura, escritura, ejecución
- Notación simbólica y octal (rwx, 755, 644)
- Usuarios, grupos, propietario y grupo de un archivo
- `sudo` y el archivo `/etc/sudoers` (concepto, sin edición directa)

### Práctica (1:00)
- `chmod` (simbólico y octal), `chown`, `chgrp`
- `umask`
- `id`, `groups`, `whoami`
- Creación de usuarios y grupos: `adduser`, `usermod`, `groupadd` (con `sudo`)
- Ejercicio: configurar un directorio compartido con permisos específicos para un grupo

---

## Módulo 5 — Redirección, tuberías y filtros básicos (1:30)

### Teoría (30 min)
- Descriptores de archivo estándar: stdin, stdout, stderr
- Redirección: `>`, `>>`, `<`, `2>`, `&>`
- Concepto de tubería (`|`) y filosofía Unix ("pequeñas herramientas encadenadas")

### Práctica (1:00)
- Combinar comandos con `|`
- Redirección de errores a archivos de log
- `tee` para redirigir y mostrar en pantalla a la vez
- `xargs` (introducción)
- Ejercicio: construir una tubería que combine `ls`, `grep` y redirección a un archivo

---

## Módulo 6 — Procesamiento de texto: grep, sed, awk, cut, sort (2:00)

### Teoría (45 min)
- Expresiones regulares básicas y extendidas (BRE/ERE)
- `grep` y sus variantes (`-i`, `-v`, `-r`, `-E`, `-c`)
- Introducción a `sed` (sustitución, borrado)
- Introducción a `awk` (campos, `$1`, `$NF`, patrones)
- `cut`, `sort`, `uniq`, `tr`

### Práctica (1:15)
- Búsqueda de patrones en logs simulados con `grep`
- Sustituciones con `sed -i` (con respaldo)
- Extracción de columnas con `awk` y `cut` desde un CSV de ejemplo
- Ordenar y contar ocurrencias con `sort | uniq -c`
- Ejercicio integrador: a partir de un archivo de log ficticio, generar un reporte de IPs más frecuentes

---

## Módulo 7 — Variables, comillas y expansión en bash (1:15)

### Teoría (30 min)
- Variables de shell vs variables de entorno (`export`)
- Comillas simples vs dobles vs backticks/`$()`
- Expansión de variables, expansión aritmética `$(( ))`, expansión de llaves `{}`
- Variables especiales: `$0`, `$?`, `$$`, `$#`, `$@`, `$*`

### Práctica (0:45)
- Declarar, exportar y usar variables
- `read` para entrada interactiva
- Sustitución de comandos y aritmética básica
- Ejercicio: script que solicite datos al usuario y los procese con variables

---

## Módulo 8 — Estructuras de control: if, case, bucles (1:30)

### Teoría (30 min)
- Condicionales: `if`, `elif`, `else`, operadores de prueba (`[ ]`, `[[ ]]`, `test`)
- `case` para múltiples opciones
- Bucles: `for`, `while`, `until`
- `break` y `continue`

### Práctica (1:00)
- Scripts con validación de condiciones (archivos existentes, números, cadenas)
- Bucle `for` recorriendo archivos de un directorio
- Bucle `while` leyendo línea a línea un archivo
- Ejercicio: script de menú interactivo usando `case`

---

## Módulo 9 — Funciones, parámetros posicionales y scripts (1:30)

### Teoría (30 min)
- Estructura de un script bash: shebang, permisos de ejecución
- Parámetros posicionales (`$1`, `$2`, `shift`)
- Definición y uso de funciones, variables locales
- Valores de retorno (`return`, `exit`) y código de salida

### Práctica (1:00)
- Convertir comandos sueltos en un script ejecutable
- Crear funciones reutilizables dentro de un script
- Manejo de argumentos con `getopts` (introducción)
- Ejercicio integrador: script de respaldo (backup) simple de una carpeta con parámetros

---

## Módulo 10 — Gestión de procesos y control de trabajos (1:00)

### Teoría (20 min)
- Concepto de proceso, PID, PPID
- Procesos en primer y segundo plano
- Señales (`SIGTERM`, `SIGKILL`, `SIGHUP`)

### Práctica (0:40)
- `ps`, `top`/`htop`, `kill`, `killall`
- `&`, `jobs`, `fg`, `bg`, `nohup`
- Ejercicio: lanzar procesos en segundo plano y gestionarlos

---

## Módulo 11 — Gestión de paquetes (APT) y servicios (systemd) (1:00)

### Teoría (20 min)
- APT y repositorios en Ubuntu 24
- Concepto de systemd y unidades de servicio

### Práctica (0:40)
- `apt update`, `apt upgrade`, `apt install`, `apt remove`, `apt search`
- `dpkg -l`, `apt list --installed`
- `systemctl status/start/stop/enable` de un servicio de ejemplo
- Ejercicio: instalar una herramienta útil (ej. `tree`, `htop`, `curl`) y verificar su servicio si aplica

---

## Módulo 12 — Automatización (cron, at) y buenas prácticas/debugging (1:00)

### Teoría (20 min)
- Sintaxis de `crontab`
- `at` para tareas puntuales
- Buenas prácticas de scripting: `set -euo pipefail`, comentarios, nombres claros
- Depuración con `bash -x` y `shellcheck`

### Práctica (0:40)
- Programar una tarea con `crontab -e`
- Validar un script con `shellcheck`
- Ejecutar script en modo debug (`bash -x script.sh`)
- Ejercicio final integrador: automatizar la ejecución periódica del script de backup del Módulo 9

---

## Evaluación sugerida
- Participación en ejercicios prácticos de cada módulo (formativa)
- Proyecto final: script bash que combine variables, control de flujo, funciones, procesamiento de texto y manejo de errores (ej. script de monitoreo o backup automatizado con logging)

---

## Bibliografía y recursos de referencia

### Documentación oficial y manuales
1. **GNU Bash Reference Manual** — Free Software Foundation. Disponible en: https://www.gnu.org/software/bash/manual/bash.html
2. **Bash man page** — `man bash` (incluida en Ubuntu 24.04)
3. **Ubuntu Server Documentation** — Canonical. Disponible en: https://ubuntu.com/server/docs
4. **Ubuntu 24.04 LTS Release Notes** — Canonical. Disponible en: https://discourse.ubuntu.com/t/noble-numbat-release-notes/
5. **Debian/Ubuntu Filesystem Hierarchy Standard (FHS)** — https://refspecs.linuxfoundation.org/FHS_3.0/fhs-3.0.html
6. **APT User's Guide** — Documentación de Debian, aplicable a Ubuntu: https://www.debian.org/doc/manuals/apt-guide/
7. **systemd Documentation** — freedesktop.org: https://www.freedesktop.org/wiki/Software/systemd/

### Libros recomendados
8. Shotts, William E. — *The Linux Command Line: A Complete Introduction* (5ª ed. o posterior), No Starch Press. Versión gratuita en PDF disponible del autor: https://linuxcommand.org/tlcl.php
9. Newham, Cameron & Rosenblatt, Bill — *Learning the bash Shell* (3ª ed.), O'Reilly Media
10. Blum, Richard & Bresnahan, Christine — *Linux Command Line and Shell Scripting Bible* (4ª ed.), Wiley
11. Robbins, Arnold & Beebe, Nelson H.F. — *Classic Shell Scripting*, O'Reilly Media
12. Sobell, Mark G. — *A Practical Guide to Ubuntu Linux*, Prentice Hall
13. Powers, Shelley et al. — *Unix Power Tools* (3ª ed.), O'Reilly Media (referencia para grep/sed/awk)

### Recursos sobre expresiones regulares y utilidades de texto
14. Friedl, Jeffrey E. F. — *Mastering Regular Expressions* (3ª ed.), O'Reilly Media
15. Dougherty, Dale & Robbins, Arnold — *sed & awk* (2ª ed.), O'Reilly Media
16. GNU grep, sed y awk (gawk) manuales oficiales: https://www.gnu.org/software/grep/manual/, https://www.gnu.org/software/sed/manual/, https://www.gnu.org/software/gawk/manual/

### Buenas prácticas y herramientas de calidad
17. **ShellCheck** (analizador estático de scripts bash) — https://www.shellcheck.net/ y https://github.com/koalaman/shellcheck
18. **Google Shell Style Guide** — https://google.github.io/styleguide/shellguide.html
19. Greg's Wiki — BashFAQ y BashGuide (comunidad, muy citado como referencia técnica): https://mywiki.wooledge.org/BashGuide y https://mywiki.wooledge.org/BashFAQ

### Cursos y plataformas complementarias (para el instructor)
20. Linux Foundation — *Introduction to Linux* (LFS101), curso gratuito en edX/Linux Foundation
21. OverTheWire — *Bandit Wargame* (ejercicios prácticos progresivos de línea de comandos Linux): https://overthewire.org/wargames/bandit/

> **Nota para el instructor:** se recomienda validar los enlaces antes de cada dictado del curso, ya que las URLs de documentación oficial pueden actualizarse. Los libros marcados pueden reemplazarse por ediciones más recientes si están disponibles al momento del dictado.
