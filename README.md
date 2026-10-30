# EduCheck — Parte 2: Frontend (React + Vite)

Interfaz web del sistema de asistencia escolar EduCheck. Consume la API del backend Django
(parte 1) a través del proxy de Vite.

> Proyecto dividido en 3 repositorios:
> 1. Backend Django — https://github.com/ROBERTHGONZALES/educheck-sistema
> 2. **Frontend React** — este repositorio
> 3. Documentación y despliegue — https://github.com/ROBERTHGONZALES/educheck-documentacion

## Requisitos

- Node.js 20.19 o superior (recomendado Node.js 22 LTS)
- El backend Django corriendo en `http://127.0.0.1:8000`

## Puesta en marcha

```bash
npm install
npm run dev
```

Abre `http://127.0.0.1:5173`.

`vite.config.ts` reenvía `/api/*` a `http://127.0.0.1:8000`, así que el backend debe estar
activo en ese puerto. Si usas otro puerto, cambia `server.proxy` en ese archivo.

## Scripts

| Comando | Descripción |
| --- | --- |
| `npm run dev` | servidor de desarrollo en 5173 |
| `npm run build` | compila a `dist/` |
| `npm run preview` | sirve `dist/` en 4173 |
| `npm run typecheck` | verificación de tipos TypeScript |

## Configuración opcional

Copia `.env.example` a `.env` para definir `VITE_CONTACT_EMAIL` (correo del botón
"Solicitar demostración" de la portada).

## Estructura

```
index.html
src/                  páginas, componentes, hooks, cliente API
packages/api-client-react/   cliente generado para la API
public/               imágenes y favicons
vite.config.ts        servidor y proxy hacia Django
```
