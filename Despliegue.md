# Proceso de Despliegue en Azure Static Web Apps

## 1. Preparación del proyecto

Se instaló el proyecto Angular:

```bash
npm install
```

Se ejecutó localmente para verificar funcionamiento:

```bash
ng serve
```

---

## 2. Inicialización de Git

```bash
git init
git add .
git commit -m "inicio proyecto"
```

Se conectó con repositorio en GitHub:

```bash
git remote add origin https://github.com/TU-USUARIO/TU-REPO.git
git push -u origin main
```

---

## 3. Creación de recurso en Azure

1. Ingresar a Azure Portal
2. Crear recurso → **Static Web Apps**
3. Seleccionar:

   * Suscripción: Azure for Students
   * Repositorio: GitHub
   * Framework: Angular

---

## 4. Configuración del despliegue

* App location:

```
/
```

* API location:

```
(vacío)
```

* Output location:

```
dist/pokedex-angular
```

---

## 5. Configuración de seguridad

Se creó el archivo:

```
staticwebapp.config.json
```

Con los siguientes encabezados:

```json
{
  "navigationFallback": {
    "rewrite": "/index.html",
    "exclude": [
      "/assets/*",
      "/*.css",
      "/*.js",
      "/*.png",
      "/*.jpg",
      "/*.jpeg",
      "/*.gif",
      "/*.svg",
      "/*.ico",
      "/*.woff",
      "/*.woff2",
      "/*.ttf"
    ]
  },
  "globalHeaders": {
    "X-Content-Type-Options": "nosniff",
    "X-Frame-Options": "DENY",
    "Referrer-Policy": "no-referrer",
    "Strict-Transport-Security": "max-age=31536000; includeSubDomains; preload",
    "Permissions-Policy": "camera=(), microphone=(), geolocation=()",
    "Content-Security-Policy": "default-src 'self'; script-src 'self' 'unsafe-inline' 'unsafe-eval' https:; style-src 'self' 'unsafe-inline' https:; img-src 'self' data: https:; font-src 'self' data: https:; connect-src 'self' https://pokeapi.co https://*.pokeapi.co; object-src 'none'; frame-ancestors 'none'; base-uri 'self'; form-action 'self'; upgrade-insecure-requests"
  }
}
```

---

## 6. Problemas encontrados y soluciones

### Error: imágenes no cargaban

**Causa:** rutas incorrectas (`/pokedex-angular/assets/...`)
**Solución:** usar rutas relativas:

```
assets/images/...
```

---

### Error: fallo en despliegue (config JSON)

**Causa:** archivo mal formateado
**Solución:** corregir estructura JSON

---

### Error: conflicto con Git

**Causa:** repositorio remoto con cambios
**Solución:**

```bash
git pull origin main --allow-unrelated-histories
```

---

## 7. Validación

* Aplicación accesible públicamente
* Sin errores en consola
* HTTPS activo
* Escaneo en securityheaders.com realizado

---


---

## Resultado final

Aplicación desplegada correctamente en Azure con medidas básicas de seguridad implementadas.
