# Estructura del Proyecto CryptoSwap

```
src/
├── app/                    # Páginas y rutas de la aplicación (Next.js 13+)
│   ├── (auth)/            # Rutas protegidas que requieren autenticación
│   ├── api/               # Endpoints de la API
│   └── layout.tsx         # Layout principal
│
├── components/            # Componentes reutilizables
│   ├── common/           # Componentes base (botones, inputs, etc.)
│   ├── features/         # Componentes específicos de features
│   │   ├── swap/        # Componentes relacionados con swaps
│   │   ├── wallet/      # Componentes relacionados con wallet
│   │   └── liquidity/   # Componentes relacionados con liquidez
│   ├── layout/          # Componentes de layout (header, footer, etc.)
│   └── ui/              # Componentes de UI puros
│
├── config/               # Configuraciones de la aplicación
│   ├── constants.ts     # Constantes globales
│   ├── networks.ts      # Configuración de redes
│   └── tokens.ts        # Configuración de tokens
│
├── hooks/               # Custom hooks
│   ├── swap/           # Hooks relacionados con swaps
│   ├── wallet/         # Hooks relacionados con wallet
│   └── common/         # Hooks de uso general
│
├── lib/                # Bibliotecas y utilidades de terceros
│   ├── solana/         # Utilidades específicas de Solana
│   └── web3/           # Utilidades generales de Web3
│
├── providers/          # Proveedores de contexto
│   ├── WalletProvider.tsx
│   └── SwapProvider.tsx
│
├── services/           # Servicios y APIs
│   ├── api/           # Servicios de API
│   ├── blockchain/    # Servicios de blockchain
│   └── storage/       # Servicios de almacenamiento
│
├── styles/            # Estilos globales
│   ├── globals.css
│   └── themes/
│
├── types/             # Definiciones de tipos TypeScript
│   ├── blockchain.ts
│   ├── swap.ts
│   └── wallet.ts
│
├── utils/             # Utilidades generales
│   ├── format.ts
│   ├── validation.ts
│   └── helpers.ts
│
└── i18n/              # Internacionalización
    ├── locales/
    └── config.ts

```

## Descripción de Directorios

### `/app`
Contiene todas las páginas y rutas de la aplicación usando el nuevo sistema de rutas de Next.js 13+.

### `/components`
- `common/`: Componentes base reutilizables
- `features/`: Componentes específicos de cada feature
- `layout/`: Componentes de estructura
- `ui/`: Componentes de UI puros

### `/config`
Configuraciones globales de la aplicación, constantes y configuraciones de red.

### `/hooks`
Custom hooks organizados por funcionalidad:
- `swap/`: Hooks relacionados con intercambios
- `wallet/`: Hooks relacionados con wallet
- `common/`: Hooks de uso general

### `/lib`
Utilidades y wrappers de bibliotecas externas:
- `solana/`: Utilidades específicas de Solana
- `web3/`: Utilidades generales de Web3

### `/providers`
Proveedores de contexto para la aplicación.

### `/services`
Servicios y APIs:
- `api/`: Servicios de API REST
- `blockchain/`: Servicios de interacción con blockchain
- `storage/`: Servicios de almacenamiento

### `/styles`
Estilos globales y temas.

### `/types`
Definiciones de tipos TypeScript organizadas por dominio.

### `/utils`
Utilidades generales y helpers.

### `/i18n`
Configuración y archivos de internacionalización.

## Convenciones de Nombrado

- **Archivos de Componentes**: PascalCase (ej: `TokenSwap.tsx`)
- **Hooks**: camelCase con prefijo 'use' (ej: `useTokenSwap.ts`)
- **Utilidades**: camelCase (ej: `formatAmount.ts`)
- **Tipos/Interfaces**: PascalCase (ej: `SwapParams.ts`)
- **Constantes**: UPPER_SNAKE_CASE (ej: `NETWORK_CONFIG.ts`)

## Mejores Prácticas

1. **Modularidad**: Mantener los componentes y lógica relacionados juntos
2. **Reutilización**: Extraer lógica común a hooks y utilidades
3. **Tipado**: Usar TypeScript para todo
4. **Testing**: Mantener tests junto al código que prueban
5. **Documentación**: Documentar componentes y funciones importantes 