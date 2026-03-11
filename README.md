# Sistema de Gestión de Biblioteca (POO + Maven)

Este proyecto implementa el enunciado solicitado aplicando:

- **Abstracción**: clase base `Libro` con atributos y comportamientos comunes.
- **Encapsulamiento**: atributos privados y acceso mediante getters/setters.
- **Herencia**: `LibroTexto` hereda de `Libro`; `LibroTextoUNIAC` hereda de `LibroTexto`; `Novela` hereda de `Libro`.

## Estructura

- `Libro`: título, autor, número de ejemplares, número de ejemplares prestados.
- `LibroTexto`: agrega `cursoAsociado`.
- `LibroTextoUNIAC`: agrega `facultadPublicadora`.
- `Novela`: agrega `tipo` (`TipoNovela`).
- `Main`: crea los 4 objetos solicitados y prueba `prestamo()` / `devolucion()`.

## Paso a paso para desarrollarlo

1. **Crear proyecto Maven**
   ```bash
   mvn archetype:generate ...
   ```
   (En este repo ya está creado el `pom.xml` mínimo).

2. **Crear la clase base `Libro`**
   - Atributos privados.
   - Constructor por defecto y constructor con parámetros.
   - Getters/setters.
   - Métodos `prestamo()` y `devolucion()` con validaciones.
   - `toString()`.

3. **Crear jerarquía de herencia**
   - `LibroTexto extends Libro`.
   - `LibroTextoUNIAC extends LibroTexto`.
   - `Novela extends Libro` y enum `TipoNovela`.

4. **Redefinir `toString()` en cada subclase**
   Para visualizar toda la información del objeto.

5. **Implementar la clase `Main`**
   - Crear `libro1` con constructor con parámetros.
   - Crear `libro2` con constructor por defecto y pedir datos por consola.
   - Crear `libroTextoUNIAC` con todos sus atributos.
   - Crear `novela` indicando su tipo.
   - Ejecutar pruebas de préstamo y devolución.

6. **Compilar y ejecutar**
   ```bash
   mvn -q compile
   mvn -q exec:java -Dexec.mainClass=com.biblioteca.Main
   ```

## Ejecución rápida (con datos simulados para `libro2`)

```bash
printf "Clean Code\nRobert C. Martin\n3\n1\n" | mvn -q exec:java -Dexec.mainClass=com.biblioteca.Main
```
