# Estructura de Páginas

## Organización de Páginas

### 1. Páginas Principales
- `/` - Página de inicio
- `/dashboard` - Dashboard principal
- `/swap` - Interfaz de intercambio
- `/wallet` - Gestión de wallet

### 2. Páginas de DeFi
- `/defi/swap` - Intercambio de tokens
- `/defi/liquidity` - Gestión de liquidez
- `/defi/staking` - Staking de tokens

### 3. Páginas de Configuración
- `/settings` - Configuración general
- `/settings/wallet` - Configuración de wallet
- `/settings/preferences` - Preferencias de usuario

## Convenciones
- Usar rutas descriptivas y en minúsculas
- Separar palabras con guiones
- Mantener la estructura de carpetas similar a la estructura de rutas
- Cada página debe tener su propio directorio con:
  - `page.tsx` - Componente principal de la página
  - `layout.tsx` - Layout específico de la página
  - `loading.tsx` - Estado de carga
  - `error.tsx` - Manejo de errores
  - `styles.module.css` - Estilos específicos

## Componentes de Página
- Mantener los componentes específicos de la página en una carpeta `components/` dentro del directorio de la página
- Reutilizar componentes comunes de `/components/ui/`
- Implementar lazy loading para componentes grandes 