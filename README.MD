# Proyecto de Productores y Consumidores

Este proyecto implementa un sistema de productores y consumidores en Java utilizando hilos y una base de datos MySQL.

## Requisitos

- Java 8 o superior
- Maven
- MySQL

## Configuración

1. Clona el repositorio:
    ```sh
    git clone <URL_DEL_REPOSITORIO>
    cd <NOMBRE_DEL_REPOSITORIO>
    ```

2. Configura la base de datos MySQL:
    - Crea una base de datos llamada `app_db`.
    - Crea una tabla llamada `persona` con la siguiente estructura:
        ```sql
        CREATE TABLE persona (
            id INT AUTO_INCREMENT PRIMARY KEY,
            nombre VARCHAR(255) NOT NULL,
            apellido VARCHAR(255) NOT NULL,
            productor VARCHAR(255) NOT NULL,
            consumidor VARCHAR(255) NOT NULL,
            fecha TIMESTAMP DEFAULT CURRENT_TIMESTAMP
        );
        ```
    - Asegúrate de tener un usuario con los permisos necesarios para acceder a esta base de datos.

3. Configura las credenciales de la base de datos en el archivo `src/main/java/org/example/Consumidor.java`:
    ```java
    conexion = DriverManager.getConnection("jdbc:mysql://<IP>:<PUERTO>/<NOMBRE_BD>", "<USUARIO>", "<CONTRASEÑA>");
    ```

## Compilación y Ejecución

1. Compila el proyecto con Maven:
    ```sh
    mvn clean install
    ```

2. Ejecuta la aplicación:
    ```sh
    mvn exec:java -Dexec.mainClass="org.example.Main"
    ```

## Estructura del Proyecto

- `src/main/java/org/example/Main.java`: Clase principal que inicia los hilos de productores y consumidores.
- `src/main/java/org/example/Productor.java`: Clase que implementa la lógica de los productores.
- `src/main/java/org/example/Consumidor.java`: Clase que implementa la lógica de los consumidores.
- `src/main/java/org/example/BufferCompartido.java`: Clase que implementa el buffer compartido entre productores y consumidores.

## Contribuciones

Las contribuciones son bienvenidas. Por favor, abre un issue o un pull request para discutir cualquier cambio que desees realizar.

## Licencia

Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo `LICENSE` para más detalles.