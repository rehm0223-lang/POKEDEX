# Pokedex Angular - Despliegue en Azure

## Descripción

Este proyecto consiste en una aplicación web desarrollada en **Angular** que permite consultar información de Pokémon utilizando la API pública de PokeAPI.

La aplicación fue desplegada en la nube utilizando **Azure Static Web Apps**, cumpliendo con buenas prácticas de seguridad mediante la configuración de encabezados HTTP.

---

## Creación de cuenta en Azure (Azure for Students)

### 1. Registro en Azure

1. Ingresar a: https://azure.microsoft.com/es-es/free/students/
2. Hacer clic en **"Comenzar gratis"**
3. Iniciar sesión con cuenta de Microsoft
4. Verificar identidad con correo institucional
5. Completar registro

---

### 2. Acceso al portal

* Ir a: https://portal.azure.com
* Iniciar sesión
* Acceder al panel principal

---

## Tecnologías utilizadas

* Angular
* TypeScript
* HTML / CSS
* Azure Static Web Apps
* PokeAPI

---

## Aplicación desplegada

URL pública: *https://wonderful-tree-0106d2a0f.7.azurestaticapps.net/*

---

## Seguridad

Se implementaron encabezados HTTP para mejorar la seguridad:

* Content-Security-Policy
* Strict-Transport-Security
* X-Content-Type-Options
* X-Frame-Options
* Referrer-Policy

---

## Instalación local

```bash
npm install
ng serve
```

Abrir en:

```
http://localhost:4200
```

---

## Build de producción

```bash
ng build --configuration production
```

---

## Estructura del proyecto

```
src/
 ├── app/
 ├── assets/
 ├── environments/
```

---

## Autor

* Rafael Hernandez
