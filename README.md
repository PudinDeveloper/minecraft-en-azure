# Servidor de Minecraft

> **Tabla de Contenido**
> 

## Minecraft en Windows

### Recursos

1. **Java 17** (Requerido para la ultima versión de Minecraft Java Edition)
    
    [Java SE 17 Archive Downloads](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html)
    
2. **Servidor de Minecraft** (Java Edition / Bedrock)
    
    [Download server for Minecraft](https://www.minecraft.net/es-es/download/server)
    
3. MCVersions.net (Lista de archivos de servidores de Minecraft Java Edition por versión)
    
    [MCVersions.net - Minecraft Versions Download List](https://mcversions.net/)
    
4. **Visual Studio Code** (Opcional, Editor de texto para modificar archivos del juego, puede usarse el block de notas en caso contrario)
    
    [Download Visual Studio Code - Mac, Linux, Windows](https://code.visualstudio.com/download)
    

### Instalación Java Edition

1. Instalar Java desde la lista de recursos, seguir los pasos del instalador y asegurarse que se está instalando la versión correcta para correr la versión deseada.
    
    <aside>
    💡 Desde la versión 1.19 de Minecraft Java Edition es necesario instalar Java 17.
    
    </aside>
    
2. Descargar el archivo de servidor de Minecraft desde la página oficial o puede usarse la pagina de MCVersions mostrada en la sección de recursos si se desea buscar una versión específica.
3. Crear una carpeta y mover dentro, nuestro archivo de servidor que debe terminar con una extension `.jar`, esto es para mantener todos los archivos generados por el servidor de manera aislada y que no causen conflicto.
4. Dentro de la misma carpeta crearemos un archivo con el nombre `iniciar.bat`.
    1. Damos click derecho al archivo y hacemos click en editar o abrir con Visual Studio Code.
    2. Una vez abierto nuestro editor de texto debemos escribir la siguiente línea.
        1. `java -Xmx5124M -Xms1024M -jar server.jar nogui`
    3. Es importante considerar que en esta línea se específica cuanta memoria RAM va utilizar el servidor al momento de iniciar y además se especifica el nombre del archivo del servidor que movimos en la carpeta.
        1. -Xmx hace referencia a la memoria máxima que puede utilizar el servidor en MB.
        2. -Xms hace referencia a la memoria mínima que puede utilizar el servidor en MB.
        3. El nombre del archivo se específica en la penúltima palabra que se muestra.
    4. Normalmente en una computadora usando Windows, el comando que se muestra en la sección **b** debería funcionar perfectamente.
5. Guardamos cambios una vez establecidos los parámetros y ejecutamos el archivo `iniciar.bat` siempre que queramos iniciar nuestro servidor.
    1. La primera vez que se inicia el servidor pedirá aceptar el [EULA](https://www.minecraft.net/es-es/eula) del juego mediante el cambio de `FALSE`a `TRUE`en el archivo EULA que se va generar.
    
    <aside>
    💡 **Visual Studio Code** permite cambiar de manera mas sencilla y visual los parametros del servidor de juego.
    
    </aside>
    
6. Una vez aceptado el [EULA](https://www.minecraft.net/es-es/eula)  es posible iniciar el servidor con parámetros preestablecidos en el archivo `server.properties` que se generará. Estas opciones dependerán de cada administrador del servidor.

### Firewall de Windows / Antivirus

1. Normalmente es posible jugar sin ningún problema, sin embargo a veces el Firewall de Windows o de cualquier programa antivirus puede bloquear las conexiones, para solucionar este problema es necesario hacer lo siguiente.
    1. Abrir el puerto `25565` o en su caso el establecido en `server.properties`.
    2. El puerto debe ser una **regla de entrada (Inbound)** y habilitada para `TCP` y `UDP`.
    3. El puerto debe ser habilitado para conexiones públicas y privadas.

## Instalación en Linux (Ubuntu)

Una vez teniendo nuestra maquina virtual debemos hacer un update y un upgrade de nuestras librerías.

```bash
# Update
sudo apt update

# Upgrade
sudo apt upgrade
```

Posteriormente debemos instalar la versión de Java 17 para usar la versión mas reciente de Minecraft Java Edition Server.

```bash
# Instalar Java 17
apt install openjdk-17-jdk openjdk-17-jre

# Comprobación de Versión
java -version
```

Una vez hecho lo anterior debemos crear una carpeta donde se van a guardar los archivos del servidor, puede ser en cualquier lugar que deseemos.

```bash
# Crear carpeta
mkdir nombreCarpeta

# Moverse dentro carpeta
cd nombreCarpeta
```

Posteriormente descargamos el archivo Java de la versión de nuestro servidor de Minecraft

```bash
wget https://[link_de_archivo_servidor.jar]
```

Una vez tenemos nuestro archivo descargado en la carpeta del servidor procedemos a crear un archivo de comandos donde vamos a ejecutar el archivo Java.

Para esto utilizaremos 2 comandos

- `touch` para crear un archivo.
- `nano` para modificar el archivo.

```bash
# Crear archivo que va arrancar nuestro servidor
touch start.bash

# Modificar el archivo para hacerlo funcionar.
nano start.bash
```

Cuando hacemos `nano` nos abrirá un editor de texto donde debemos escribir lo siguiente.

```bash
java -Xmx5124M -Xms1024M -jar server.jar nogui
```

- Es importante considerar que en esta línea se específica cuanta memoria RAM va utilizar el servidor al momento de iniciar y además se especifica el nombre del archivo del servidor que movimos en la carpeta.
    1. -Xmx hace referencia a la memoria máxima que puede utilizar el servidor en MB.
    2. -Xms hace referencia a la memoria mínima que puede utilizar el servidor en MB.
    3. El nombre del archivo se específica en la penúltima palabra que se muestra.

Una vez terminado todo este proceso, para arrancar nuestro servidor utilizaremos el siguiente comando.

```bash
bash start.bash
```

Aquí la primera vez nos pedirá aceptar el eula, utilzaremos el comando `nano` para modifcar el archivo del [EULA](https://www.minecraft.net/es-es/eula) y cambiar el parametro `false` por `true`.

Una vez aceptado el [EULA](https://www.minecraft.net/es-es/eula)  es posible iniciar el servidor con parámetros preestablecidos en el archivo `server.properties` que se generará. Estas opciones dependerán de cada administrador del servidor.

Posteriormente volvemos a ejecutar el comando anterior de `bash` y el servidor arrancará sin problema alguno si todos los parámetros son correctos.
