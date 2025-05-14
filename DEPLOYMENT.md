# Guía de Despliegue

## 🚀 Preparación

1. **Variables de Entorno**
   ```bash
   # Copiar y configurar variables
   cp .env.example .env.production
   ```

2. **Build de Producción**
   ```bash
   npm run build
   ```

## 🌐 Opciones de Despliegue

### Vercel (Recomendado)

1. **Instalación**
   ```bash
   npm i -g vercel
   ```

2. **Despliegue**
   ```bash
   vercel
   ```

### Docker

1. **Construir Imagen**
   ```bash
   docker build -t cryptoswap .
   ```

2. **Ejecutar Contenedor**
   ```bash
   docker run -p 3000:3000 cryptoswap
   ```

## 🔒 Configuración de Seguridad

1. **CSP**
   - Configurar en `next.config.js`
   - Actualizar según necesidades

2. **Rate Limiting**
   - Configurar en servidor
   - Ajustar límites según uso

3. **SSL/TLS**
   - Configurar certificados
   - Forzar HTTPS

## 📊 Monitoreo

1. **Logs**
   - Configurar sistema de logs
   - Monitorear errores

2. **Métricas**
   - Implementar analytics
   - Monitorear rendimiento

## 🔄 CI/CD

1. **GitHub Actions**
   ```yaml
   name: Deploy
   on:
     push:
       branch: main
   ```

2. **Automatización**
   - Tests automáticos
   - Build automático
   - Despliegue automático

## 🛠️ Mantenimiento

1. **Backups**
   - Configurar backups regulares
   - Verificar restauración

2. **Actualizaciones**
   - Mantener dependencias actualizadas
   - Revisar seguridad

## 🚨 Troubleshooting

1. **Errores Comunes**
   - Problemas de conexión
   - Errores de build
   - Problemas de memoria

2. **Solución**
   - Revisar logs
   - Verificar configuración
   - Contactar soporte

## Tabla de Contenidos

- [Requisitos Previos](#requisitos-previos)
- [Configuración del Entorno](#configuración-del-entorno)
- [Despliegue en Desarrollo](#despliegue-en-desarrollo)
- [Despliegue en Producción](#despliegue-en-producción)
- [Monitoreo y Mantenimiento](#monitoreo-y-mantenimiento)
- [Solución de Problemas](#solución-de-problemas)

## Requisitos Previos

- Node.js >= 16.x
- npm >= 8.x
- Git
- Cuenta en Vercel (para despliegue)
- Cuenta en Solana (para configuración de red)

## Configuración del Entorno

1. **Variables de Entorno**

   Crea un archivo `.env.local` con las siguientes variables:

   ```env
   NEXT_PUBLIC_SOLANA_NETWORK=mainnet-beta
   NEXT_PUBLIC_RPC_ENDPOINT=https://api.mainnet-beta.solana.com
   NEXT_PUBLIC_PROGRAM_ID=tu_program_id
   ```

2. **Configuración de Solana**

   ```bash
   # Instalar CLI de Solana
   sh -c "$(curl -sSfL https://release.solana.com/v1.14.0/install)"

   # Configurar red
   solana config set --url https://api.mainnet-beta.solana.com
   ```

## Despliegue en Desarrollo

1. **Instalación de Dependencias**

   ```bash
   npm install
   ```

2. **Ejecutar en Desarrollo**

   ```bash
   npm run dev
   ```

3. **Pruebas**

   ```bash
   # Ejecutar pruebas
   npm test

   # Ejecutar pruebas e2e
   npm run test:e2e
   ```

## Despliegue en Producción

### Despliegue en Vercel

1. **Preparación**

   ```bash
   # Construir la aplicación
   npm run build

   # Verificar la construcción
   npm run start
   ```

2. **Configuración en Vercel**

   - Conecta tu repositorio de GitHub
   - Configura las variables de entorno
   - Configura el dominio personalizado
   - Habilita HTTPS

3. **Despliegue Automático**

   - Los cambios en `main` se despliegan automáticamente
   - Las preview deployments se crean para cada PR

### Despliegue Manual

1. **Construir la Aplicación**

   ```bash
   npm run build
   ```

2. **Desplegar**

   ```bash
   # Usando Vercel CLI
   vercel --prod

   # O usando el dashboard de Vercel
   vercel
   ```

## Monitoreo y Mantenimiento

1. **Monitoreo**

   - Usa Vercel Analytics para métricas de rendimiento
   - Configura alertas para errores
   - Monitorea el uso de la API de Solana

2. **Mantenimiento**

   ```bash
   # Actualizar dependencias
   npm update

   # Verificar vulnerabilidades
   npm audit

   # Limpiar caché
   npm cache clean --force
   ```

3. **Backups**

   - Realiza backups regulares de la base de datos
   - Mantén copias de seguridad de las claves privadas
   - Documenta los cambios importantes

## Solución de Problemas

### Problemas Comunes

1. **Error de Conexión a Solana**
   - Verifica la configuración de RPC
   - Comprueba el estado de la red
   - Verifica las credenciales

2. **Errores de Construcción**
   - Limpia la caché: `npm run clean`
   - Verifica las dependencias
   - Revisa los logs de construcción

3. **Problemas de Despliegue**
   - Verifica las variables de entorno
   - Comprueba los límites de la API
   - Revisa los logs de Vercel

### Recursos Adicionales

- [Documentación de Vercel](https://vercel.com/docs)
- [Documentación de Solana](https://docs.solana.com)
- [Soporte de Next.js](https://nextjs.org/docs)

## Contacto

Para soporte técnico o preguntas sobre el despliegue:
- Abre un issue en GitHub
- Contacta al equipo de DevOps
- Consulta la documentación oficial 