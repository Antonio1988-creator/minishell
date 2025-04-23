# Minishell :shell:

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Español :es:

### Descripción
Minishell es un shell básico inspirado en bash, desarrollado como proyecto educativo. Implementa las funcionalidades principales de un intérprete de comandos.

### Características principales
- :computer: Prompt interactivo con historial (usando readline)
- :mag_right: Búsqueda de comandos (PATH, rutas absolutas/relativas)
- :arrows_counterclockwise: Pipes múltiples (`cmd1 | cmd2 | cmd3`)
- :left_right_arrow: Redirecciones:
  - `<` entrada
  - `>` salida (sobrescritura)
  - `<<` here-document
  - `>>` salida (append)
- :dollar: Expansión de variables (`$VAR`, `$?`)
- :signal_strength: Manejo de señales (Ctrl-C, Ctrl-D, Ctrl-\)
- :gear: Built-ins:
  - `echo` con opción `-n`
  - `cd`
  - `pwd`
  - `export`
  - `unset`
  - `env`
  - `exit`

### Requisitos
- Compilador C (gcc/clang)
- GNU Make
- Biblioteca readline (`sudo apt-get install libreadline-dev`)

### Compilación
```bash
make

### Ejecución
```bash
./minishell

## Bugs conocidos :bug:

- **`Ctrl + \` (`SIGQUIT`)**: Muestra caracter `^\` aunque no debería aparecer
- **`$SHLVL`**: No gestiona niveles de profundidad de shell
- **`SIGINT` en heredoc**: Comportamiento incorrecto (debería cerrar el fichero)
- **Exit code en pipes**: Con comandos no encontrados (`s` en `cmd1 | s | cmd2`) no siempre retorna el código esperado
- **`SIGPIPE` (141)**: En pipes complejos, a veces retorna este código en vez del esperado

## Autores
[Antonio Guil] - [https://github.com/Antonio1988-creator]
[Pablo Abad] - [https://github.com/pabloabap]


# Minishell :shell:

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Description
Minishell is a basic shell inspired by bash, developed as an educational project. It implements the core functionality of a command interpreter.

## Main Features
- :computer: Interactive prompt with history (using readline)
- :mag_right: Command search (PATH, absolute/relative paths)
- :arrows_counterclockwise: Multiple pipes (`cmd1 | cmd2 | cmd3`)
- :left_right_arrow: Redirections:
  - `<` input
  - `>` output (overwrite)
  - `<<` here-document
  - `>>` output (append)
- :dollar: Variable expansion (`$VAR`, `$?`)
- :signal_strength: Signal handling (Ctrl-C, Ctrl-D, Ctrl-\)
- :gear: Built-ins:
  - `echo` with `-n` option
  - `cd`
  - `pwd`
  - `export`
  - `unset`
  - `env`
  - `exit`

## Requirements
- C compiler (gcc/clang)
- GNU Make
- Readline library (`sudo apt-get install libreadline-dev`)

## Compilation
```bash
make

### Execution
```bash
./minishell

## Known Bugs :bug:

- **`Ctrl + \` (`SIGQUIT`)**: Shows `^\` character when it shouldn't appear
- **`$SHLVL`**: Doesn't handle shell nesting levels  
- **`SIGINT` in heredoc**: Incorrect behavior (should close the file)
- **Exit code in pipes**: With not found commands (`s` in `cmd1 | s | cmd2`) doesn't always return expected exit code
- **`SIGPIPE` (141)**: In complex pipes, sometimes returns this code instead of expected one

## Authors
[Antonio Guil] - [https://github.com/Antonio1988-creator]
[Pablo Abad] - [https://github.com/pabloabap]
