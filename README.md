# ServerChecker

### Resumen del Funcionamiento:

El script checkServer está diseñado para resolver los registros PTR de una lista de dominios proporcionada en un archivo de texto con extensión .in. 
Utiliza las bibliotecas estándar de Python para interactuar con DNS y realizar operaciones de entrada/salida.

El objetivo principal es obtener el registro A de los dominios y, en consecuencia, determinar el hostname del servidor al cual corresponde dicho registro A.
Es decir, determina en que servidor se encuentra alojado el sitio web de los dominios.

1. **Verificación del Archivo de Entrada:** El script verifica que se haya proporcionado un nombre de archivo como argumento de línea de comandos y que este tenga la extensión .in. Si no cumple con estas condiciones, muestra un mensaje de error y termina la ejecución.

2. **Lectura del Archivo de Dominios:** El script lee la lista de dominios desde el archivo proporcionado. Cada dominio debe estar en una línea separada en el archivo.

3. **Resolución de Registros:** Para cada dominio en la lista, el script realiza consultas DNS para resolver su registro A y PTR correspondiente.

4. **Escritura en Archivo CSV:** Después de resolver todos los registros PTR, el script escribe la lista de dominios y sus registros PTR asociados en un archivo CSV con el mismo nombre que el archivo de entrada, pero con la extensión .csv.

### Uso:

Para utilizar el script, sigue estos pasos:

- Asegúrate de tener instalado Python 3 en tu sistema.
- Crea un archivo de texto con la lista de dominios que deseas verificar. Asegúrate de que el archivo tenga la extensión .in y que cada dominio esté en una línea separada.- Dale permisos de ejecución con el siguiente comando: `chmod +x checkServer`
- Ejecuta el script desde la línea de comandos, pasando el nombre del archivo de la lista de dominios como argumento:

```
./checkServer <listadoDominios.in>
```

Ejemplo: 
```
./checkServer dominios.in
```

### Ejemplo de archivo de entrada:

dominios.in:
```
dominio1
dominio2
...
dominioN
```

### Ejemplo de archivo de salida: 
dominios.csv:
```
Dominio,PTR
dominio1,PTR1
dominio2,PTR2
...
dominioN,PTRN
```