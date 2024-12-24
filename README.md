# TheMailWebEnum

TheMailWebEnum es un script Python diseñado para probar si un correo electrónico está registrado en un formulario de login web vulnerable. Este proyecto permite realizar pruebas utilizando técnicas de enumeración basadas en las respuestas del servidor.
Características

 - Interfaz interactiva para configurar la prueba.
 -  Soporte para detectar emails registrados o no registrados mediante cadenas personalizadas.
 - Opción para usar proxy en las solicitudes.
 - Entrada manual de emails o carga desde un archivo.
 - Ejecución concurrente para mejorar la velocidad.
 - Manejo seguro de interrupciones (Ctrl+C) para detener la ejecución sin errores.
 - Depuración opcional para analizar respuestas del servidor.

## Requisitos

 Python 3.7 o superior.
   ### Las siguientes dependencias:
   
 requests
 termcolor
 concurrent.futures (incluido en Python estándar)

Puedes instalar las dependencias ejecutando:

`pip install requests termcolor`

## Instalación

 Clona este repositorio:

`git clone[ https://github.com/TheOffSecGirl/TheMailWebEnum.git](https://github.com/theoffsecgirl/TheEmailWebEnum.git)`

Navega al directorio del proyecto:

    cd TheMailWebEnum

    //Asegúrate de que los requisitos estén instalados.

## Uso

Ejecuta el script usando:

`python3 TheMailWebEnum.py`

### Configuración interactiva

- URL del formulario: Introduce la URL del formulario de login que deseas probar.
- Campos del formulario: Especifica los nombres de los campos para el email y la contraseña (por defecto: email y password).
-  Cadenas de respuesta: Ingresa cadenas que indiquen si un email es válido o inválido (por ejemplo, "no existe" para inválido, "contraseña incorrecta" para válido).
- Proxy (opcional): Proporciona un proxy en formato http://ip:puerto si necesitas enviar solicitudes a través de uno.
- Emails: Puedes introducir emails manualmente o cargar una lista desde un archivo.

### Manejo de interrupciones

Si necesitas detener el script durante la ejecución, presiona Ctrl+C. El programa cerrará correctamente todos los hilos y detendrá la ejecución sin generar errores o resultados incompletos.
Depuración

En caso de resultados indeterminados, el script muestra las primeras 500 letras de la respuesta del servidor para facilitar la revisión manual.
Ejemplo de Ejecución
````
  _____   _             ___     __    __   ___               ___   _         _
 |_   _| | |_    ___   / _ \   / _|  / _| / __|  ___   __   / __| (_)  _ _  | |
   | |   | ' \  / -_) | (_) | |  _| |  _| \__ \ / -_) / _| | (_ | | | | '_| | |
   |_|   |_||_| \___|  \___/  |_|   |_|   |___/ \___| \__|  \___| |_| |_|   |_|
                                     by TheOffSecGirl

Ingresa la URL del formulario de login: http://127.0.0.1:3000/login
Ingresa el nombre del campo para el email (por defecto: email):
Ingresa el nombre del campo para la contraseña (por defecto: password):
Ingresa cadenas que indican email inválido, separadas por comas (por defecto: 'no existe,usuario no encontrado'):
Ingresa cadenas que indican email válido, separadas por comas (por defecto: 'contraseña incorrecta,password incorrecto'):
Ingresa un proxy (opcional, formato http://ip:puerto):
Ingresa '1' para introducir emails manualmente o '2' para cargar desde un archivo: 1
Ingresa los emails a probar (separados por comas): test1@example.com,test2@example.com

[+] Probando emails en la URL: http://127.0.0.1:3000/login
[*] Probando email: test1@example.com
[-] El email test1@example.com no está registrado.
[*] Probando email: test2@example.com
[+] El email test2@example.com está registrado.

````

# Autora

Creado con ❤️ por TheOffSecGirl.

## Contribuciones

¿Tienes ideas para mejorar este proyecto? ¡Las contribuciones son bienvenidas! Haz un fork del repositorio y envía un pull request.
Licencia

Este proyecto está licenciado bajo la MIT License.
