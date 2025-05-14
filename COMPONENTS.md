# Estructura de Componentes

## Organización de Componentes

### 1. Componentes UI (`/components/ui/`)
Componentes de interfaz de usuario reutilizables y básicos.
- Botones
- Inputs
- Modales
- Cards
- etc.

### 2. Componentes DeFi (`/components/defi/`)
Componentes específicos para funcionalidades DeFi.
- Swap
- Liquidez
- Staking
- etc.

### 3. Componentes de Wallet (`/components/wallet/`)
Componentes relacionados con la gestión de wallets.
- Conexión de wallet
- Visualización de balance
- Gestión de tokens

### 4. Componentes de Dashboard (`/components/dashboard/`)
Componentes para la visualización de datos y estadísticas.
- Gráficos
- Tablas
- Indicadores

### 5. Componentes de Providers (`/components/providers/`)
Componentes que proporcionan contexto y funcionalidad a la aplicación.
- Providers de estado
- Providers de tema
- Providers de autenticación

## Convenciones de Nombrado
- Usar PascalCase para nombres de componentes
- Usar kebab-case para nombres de archivos
- Agregar sufijo `.tsx` para componentes con JSX
- Agregar sufijo `.ts` para componentes sin JSX

## Estructura de Archivos
Cada componente debe tener su propia carpeta con:
- `index.tsx` - Componente principal
- `styles.module.css` - Estilos específicos del componente
- `types.ts` - Tipos específicos del componente
- `utils.ts` - Utilidades específicas del componente
- `__tests__/` - Pruebas del componente 