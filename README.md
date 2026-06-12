# Proyecto Ensamblador 88110 - UPM
## Preparación del Entorno

Dado que los ejecutables del emulador son pesados y dependientes del sistema, **no** se suben a GitHub (están ignorados en el `.gitignore`). La primera vez que vayas a trabajar, sigue estos pasos:

1. Abre tu terminal (PowerShell o CMD) y clona el repositorio en tu carpeta de Documentos:
   ```cmd
   git clone https://github.com/ghit2025/Proyecto-88110-UPM.git
2. Entra en el directorio recién clonado:
```cmd
cd Proyecto-88110-UPM

```
3. Descarga el paquete de herramientas de Windows (`88k_Windows_v11`) desde la web de la asignatura.
4. Extrae y **copia** los siguientes archivos directamente en la raíz de la carpeta del repositorio:
* `88110.exe` (Simulador)
* `88110e.exe` (Ensamblador)
* `cygwin1.dll` (Librería de entorno)
* `serie` (Fichero de configuración)
* `mc88110.bat` (Script de ejecución)
---

## COMO TRABAJAR CON EL PROYECTO
 Seguir estos 5 pasos:

### 1º Hacer pull por si acaso se ha cambiado algo

```cmd
git pull origin main

```

### 2º Programar

Abriremos nuestro editor (recomendado VS Code) y trabajaremos **exclusivamente** sobre * **Fichero:** `CDV25.ens`

### 3º Ensamblar/Compilar

Cada vez que terminemos un bloque lógico o queramos probar una subrutina, debemos ensamblar el fichero para pasarlo a binario. En la terminal ejecutamos:

```cmd
88110e.exe CDV25.ens

```

*Nota: Si el código está libre de errores de sintaxis, se generará el archivo `CDV25.bin` de forma transparente.*

### 4º Simular y Depurar

Para verificar el comportamiento de los registros, la memoria y la pila, invocamos al simulador pasándole el binario que acabamos de ensamblar:

```cmd
mc88110.bat CDV25.bin

```

*(Si el .bat te da algún problema, puedes lanzarlo manualmente con: `88110.exe serie CDV25.bin`)*

### 5º Guardar y Subir (Commit & Push)

```cmd
git add .
git commit -m "Descripción clara de lo que hace (ej. 'rutina BuscaCar implementada y testeada')"
git push origin main

```
