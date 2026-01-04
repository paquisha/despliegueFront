# Configuración para Vercel

## Variables de Entorno

Crea un archivo `.env.local` en la raíz del proyecto para desarrollo local:

```env
VITE_API_URL=http://localhost:3001/api
```

**Importante**: Para producción en Vercel, configura esta variable en el Dashboard de Vercel:
- Ve a tu proyecto en [vercel.com](https://vercel.com)
- Ve a **Settings** → **Environment Variables**
- Agrega `VITE_API_URL` con la URL de tu backend desplegado
- Ejemplo: `https://tu-backend.railway.app/api`
- Selecciona los entornos donde aplicará (Production, Preview, Development)

## Despliegue Rápido

1. **Asegúrate de que el código esté en un repositorio Git** (GitHub, GitLab, Bitbucket)

2. **Ve a [vercel.com](https://vercel.com)** e inicia sesión

3. **Importa el proyecto**:
   - Haz clic en "Add New Project"
   - Conecta tu repositorio Git
   - Selecciona este repositorio

4. **Configuración automática**:
   - Vercel detectará automáticamente que es un proyecto Vite
   - El archivo `vercel.json` ya está configurado con las rewrites necesarias para el routing SPA
   - No necesitas configurar manualmente Build Command ni Output Directory (se detectan automáticamente)

5. **Agrega la variable de entorno `VITE_API_URL`** (paso 2 de Variables de Entorno)

6. **Haz clic en "Deploy"** 🚀

## Notas Importantes

- El archivo `vercel.json` está configurado para manejar el routing de React Router (SPA)
- Las variables de entorno que empiezan con `VITE_` son expuestas al cliente en tiempo de build
- Después del despliegue, cualquier cambio que hagas en la rama principal se desplegará automáticamente

