# Documentación de API - CryptoSwap

## Hooks

### useWallet

Hook para manejar la conexión y gestión de wallets de Solana.

```typescript
const {
  publicKey,
  connected,
  connecting,
  wallet,
  wallets,
  error,
  connectWallet,
  disconnect,
  isAutoConnecting,
} = useWallet();
```

#### Propiedades

| Propiedad | Tipo | Descripción |
|-----------|------|-------------|
| publicKey | `PublicKey \| null` | Clave pública de la wallet conectada |
| connected | `boolean` | Estado de conexión de la wallet |
| connecting | `boolean` | Estado de conexión en proceso |
| wallet | `Wallet \| null` | Instancia de la wallet conectada |
| wallets | `Wallet[]` | Lista de wallets disponibles |
| error | `Error \| null` | Error de conexión si existe |
| isAutoConnecting | `boolean` | Estado de auto-conexión |

#### Métodos

| Método | Parámetros | Retorno | Descripción |
|--------|------------|---------|-------------|
| connectWallet | `walletName: string` | `Promise<void>` | Conecta una wallet específica |
| disconnect | - | `Promise<void>` | Desconecta la wallet actual |

### useSolanaConnection

Hook para manejar la conexión con la red Solana.

```typescript
const {
  connection,
  isConnecting,
  error,
  getBalance,
  getTokenAccounts,
  initializeConnection,
} = useSolanaConnection();
```

#### Propiedades

| Propiedad | Tipo | Descripción |
|-----------|------|-------------|
| connection | `Connection \| null` | Instancia de conexión con Solana |
| isConnecting | `boolean` | Estado de conexión en proceso |
| error | `Error \| null` | Error de conexión si existe |

#### Métodos

| Método | Parámetros | Retorno | Descripción |
|--------|------------|---------|-------------|
| getBalance | `publicKey: PublicKey` | `Promise<number>` | Obtiene el balance de una cuenta |
| getTokenAccounts | `publicKey: PublicKey` | `Promise<ParsedAccountInfo[]>` | Obtiene las cuentas de tokens |
| initializeConnection | - | `Promise<void>` | Inicializa la conexión con Solana |

## Configuración

### SOLANA_CONFIG

Configuración de la red Solana.

```typescript
const SOLANA_CONFIG = {
  MAINNET: 'mainnet-beta',
  TESTNET: 'testnet',
  DEVNET: 'devnet',
  DEFAULT_ENDPOINT: 'https://api.mainnet-beta.solana.com',
  ENDPOINTS: {
    'mainnet-beta': 'https://api.mainnet-beta.solana.com',
    testnet: 'https://api.testnet.solana.com',
    devnet: 'https://api.devnet.solana.com',
  },
  COMMITMENT: 'confirmed',
  TIMEOUT: 60000,
};
```

### WALLET_CONFIG

Configuración de wallets.

```typescript
const WALLET_CONFIG = {
  SUPPORTED_WALLETS: [
    'Phantom',
    'Solflare',
    'Clover',
    'Alpha',
    'Avana',
  ],
  AUTO_CONNECT: true,
  CONNECTION_TIMEOUT: 10000,
};
```

## Ejemplos de Uso

### Conectar Wallet

```typescript
const { connectWallet } = useWallet();

// Conectar Phantom
await connectWallet('Phantom');
```

### Obtener Balance

```typescript
const { getBalance } = useSolanaConnection();
const { publicKey } = useWallet();

if (publicKey) {
  const balance = await getBalance(publicKey);
  console.log('Balance:', balance / 1e9, 'SOL');
}
```

### Obtener Cuentas de Tokens

```typescript
const { getTokenAccounts } = useSolanaConnection();
const { publicKey } = useWallet();

if (publicKey) {
  const tokenAccounts = await getTokenAccounts(publicKey);
  console.log('Token Accounts:', tokenAccounts);
}
```

## Manejo de Errores

Todos los métodos que interactúan con la red Solana pueden lanzar errores. Es importante manejar estos errores adecuadamente:

```typescript
try {
  await connectWallet('Phantom');
} catch (error) {
  console.error('Error al conectar wallet:', error);
  // Mostrar mensaje al usuario
}
```

## Mejores Prácticas

1. **Verificar Conexión**: Siempre verifica el estado de conexión antes de realizar operaciones.
2. **Manejo de Errores**: Implementa manejo de errores adecuado en todas las operaciones.
3. **Auto-conexión**: Utiliza la auto-conexión para mejorar la experiencia del usuario.
4. **Caché**: Implementa caché para datos que no cambian frecuentemente.
5. **Validación**: Valida los datos antes de realizar operaciones en la red.

## Endpoints Principales

### Swap API
```typescript
/**
 * @method POST /api/swap
 * @description Ejecuta un intercambio de tokens
 * @param {SwapRequest} request - Parámetros del swap
 * @returns {SwapResponse} Resultado del intercambio
 * @security BearerAuth
 */
interface SwapRequest {
  inputToken: string;
  outputToken: string;
  amount: number;
  slippage: number;
}

interface SwapResponse {
  txHash: string;
  estimatedAmount: number;
  fee: number;
}
```