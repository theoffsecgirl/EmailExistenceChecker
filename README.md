# TheEmailWebEnum

TheEmailWebEnum es un script de Python diseñado para verificar la existencia de correos electrónicos en formularios de inicio de sesión web. Este script es una herramienta útil para realizar pruebas en entornos de bug bounty y otras auditorías de seguridad.

---

## Características

- **Configuración Dinámica:** Permite configurar los nombres de los campos del formulario (por ejemplo, email y password).
- **Compatibilidad con Proxies:** Soporte para redirigir el tráfico a través de un proxy como Burp Suite.
- **Cadenas Personalizables:** Puedes definir las cadenas que indican si un correo electrónico es válido o no.
- **Entrada Flexible:** Opción para cargar correos desde un archivo o ingresarlos manualmente.
- **Detección Inteligente:** Clasifica automáticamente los resultados en correos válidos, inválidos o indeterminados.

---

## Requisitos

- **Python 3.6+**
- Módulos necesarios:
  - `requests`
  - `bs4` (BeautifulSoup)
  - `termcolor`

Para instalar los módulos requeridos, ejecuta:

```bash
pip install requests beautifulsoup4 termcolor
```

---

## Uso

1. **Ejecuta el script:**

   ```bash
   python3 TheEmailWebEnum.py
   ```

2. **Sigue las instrucciones interactivas:**

   - Ingresa la URL del formulario de inicio de sesión.
   - Especifica los nombres de los campos del formulario.
   - Proporciona las cadenas que indican correos válidos o inválidos.
   - Ingresa un proxy (opcional).
   - Elige entre ingresar correos manualmente o cargarlos desde un archivo.

3. **Resultados:**

   Los resultados serán clasificados como:

   - **Válidos:** Correos electrónicos que existen en el sistema.
   - **Inválidos:** Correos electrónicos que no están registrados.
   - **Indeterminados:** Respuestas ambiguas que requieren revisión manual.

---

## Ejemplo

### Entrada

```text
URL: http://example.com/login
Campo de email: email
Campo de password: password
Cadenas de error: usuario no encontrado, no existe
Cadenas de éxito: contraseña incorrecta, password incorrecto
Proxy: http://127.0.0.1:8080
Archivo de correos: emails.txt
```

### Salida

```text
[*] Probando email: test@example.com
[-] El email test@example.com no está registrado.

[*] Probando email: admin@example.com
[+] El email admin@example.com está registrado.
```

---

## Advertencia

Este script debe ser utilizado únicamente en entornos donde tengas permiso explícito para realizar auditorías de seguridad. El uso no autorizado puede violar leyes y términos de servicio.

---

## Autora

Creado con ❤️ por **TheOffSecGirl**.

---

## Contribuciones

¿Tienes ideas para mejorar este proyecto? ¡Las contribuciones son bienvenidas! Haz un fork del repositorio y envía un pull request.

---

## Licencia

Este proyecto está licenciado bajo la [MIT License](https://opensource.org/licenses/MIT).

