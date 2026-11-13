# jwt-lab-heidi

Laboratorio de Desarrollo de Software Seguro enfocado en identificar, explotar y corregir vulnerabilidades de autenticación mediante JSON Web Tokens (JWT).

## Tecnologías
- Python y Flask
- PyJWT
- Requests

## Vulnerabilidades analizadas

Se implementó una API vulnerable y se realizaron tres pruebas de seguridad:

1. **JWT sin firma (`alg: none`):** modificación del rol de usuario para obtener acceso administrativo.
2. **Clave secreta débil:** descubrimiento de la clave mediante un ataque de diccionario.
3. **Token sin expiración ni revocación:** reutilización de un JWT después del cierre de sesión.

## Correcciones implementadas

- Verificación de firmas con HS256.
- Expiración de tokens después de 15 minutos.
- Clave secreta aleatoria almacenada en `.env`.
- Revocación de JWT mediante identificadores únicos (`jti`).
- Validación de roles desde los datos del servidor.

## Ejecución 

1. Clonar el repositorio y abrir la carpeta del proyecto.
2. Crear y activar el entorno virtual:
   - `python -m venv venv`
   - `.\venv\Scripts\Activate.ps1`
3. Instalar las dependencias:
   - `python -m pip install -r requirements.txt`
4. Crear un archivo `.env` con una variable `JWT_SECRET` segura.
5. Ejecutar la API:
   - `python app.py`

## Conclusión

El laboratorio permitió demostrar que la seguridad de JWT depende de una correcta validación de firmas, el uso de claves robustas y la gestión adecuada de la expiración y revocación de tokens.

**Nota:** Proyecto desarrollado con fines educativos en un entorno local controlado.