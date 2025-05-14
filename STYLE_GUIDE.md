# Guía de Estilo

Esta guía establece los estándares de código y estilo para el proyecto CryptoSwap.

## 📝 Convenciones Generales

### Nombrado

- **Archivos**: kebab-case
  ```typescript
  // ✅ Correcto
  use-wallet.ts
  token-swap.tsx
  
  // ❌ Incorrecto
  useWallet.ts
  TokenSwap.tsx
  ```

- **Componentes**: PascalCase
  ```typescript
  // ✅ Correcto
  const TokenSwap: React.FC = () => {};
  
  // ❌ Incorrecto
  const tokenSwap: React.FC = () => {};
  ```

- **Hooks**: camelCase
  ```typescript
  // ✅ Correcto
  const useWallet = () => {};
  
  // ❌ Incorrecto
  const UseWallet = () => {};
  ```

### Estructura de Archivos

```
src/
  ├── components/
  │   ├── common/
  │   └── features/
  ├── hooks/
  ├── utils/
  ├── types/
  └── pages/
```

## 💅 Estilo de Código

### TypeScript

```typescript
// Interfaces
interface WalletProps {
  address: string;
  balance: number;
}

// Tipos
type TokenSymbol = 'SOL' | 'USDC' | 'BTC';

// Enums
enum TransactionStatus {
  PENDING = 'pending',
  COMPLETED = 'completed',
  FAILED = 'failed'
}
```

### React

```typescript
// Componentes
const TokenCard: React.FC<TokenCardProps> = ({ symbol, balance }) => {
  return (
    <div className="token-card">
      <h3>{symbol}</h3>
      <p>{balance}</p>
    </div>
  );
};

// Hooks
const useTokenBalance = (address: string) => {
  const [balance, setBalance] = useState<number>(0);
  // ...
};
```

### CSS/Tailwind

```typescript
// Clases
<div className="flex items-center justify-between p-4 bg-white rounded-lg shadow-md">
  <h2 className="text-xl font-bold text-gray-800">
    {title}
  </h2>
</div>
```

## 📚 Documentación

### JSDoc

```typescript
/**
 * Hook para manejar la conexión de wallet
 * @param {string} network - Red de Solana a conectar
 * @returns {Object} Objeto con métodos de wallet
 * @example
 * const { connect, disconnect } = useWallet('mainnet-beta');
 */
```

### Comentarios

```typescript
// Comentarios de una línea
const MAX_RETRIES = 3;

/* 
 * Comentarios de múltiples líneas
 * para explicar lógica compleja
 */
```

## 🧪 Testing

```typescript
describe('useWallet', () => {
  it('should connect to wallet', async () => {
    // Arrange
    const { result } = renderHook(() => useWallet());
    
    // Act
    await act(async () => {
      await result.current.connect();
    });
    
    // Assert
    expect(result.current.isConnected).toBe(true);
  });
});
```

## 🔍 Linting

- Usar ESLint
- Configurar Prettier
- Seguir reglas de TypeScript

## 🚀 Mejores Prácticas

1. **Performance**
   - Usar memoización
   - Optimizar renders
   - Lazy loading

2. **Seguridad**
   - Validar inputs
   - Sanitizar datos
   - Manejar errores

3. **Accesibilidad**
   - Usar roles ARIA
   - Mantener contraste
   - Soporte keyboard

## Tabla de Contenidos

- [General](#general)
- [TypeScript](#typescript)
- [React](#react)
- [CSS/Tailwind](#csstailwind)
- [Testing](#testing)
- [Documentación](#documentación)
- [Git](#git)

## General

### Estructura de Archivos

```
src/
  ├── components/     # Componentes reutilizables
  ├── hooks/         # Custom hooks
  ├── pages/         # Páginas de Next.js
  ├── styles/        # Estilos globales
  ├── utils/         # Utilidades
  ├── types/         # Definiciones de tipos
  └── config/        # Configuraciones
```

### Convenciones de Nombrado

- **Archivos**: PascalCase para componentes, camelCase para utilidades
  ```
  Button.tsx
  useWallet.ts
  ```

- **Componentes**: PascalCase
  ```typescript
  const Button = () => {};
  ```

- **Hooks**: camelCase, prefijo 'use'
  ```typescript
  const useWallet = () => {};
  ```

- **Utilidades**: camelCase
  ```typescript
  const formatBalance = () => {};
  ```

## TypeScript

### Tipos

- Usa interfaces para objetos que representan entidades
- Usa type para uniones y tipos primitivos
- Evita `any`, usa `unknown` si es necesario

```typescript
interface Wallet {
  publicKey: PublicKey;
  connected: boolean;
}

type Network = 'mainnet' | 'testnet' | 'devnet';
```

### Genéricos

- Usa genéricos para funciones reutilizables
- Proporciona nombres descriptivos para parámetros genéricos

```typescript
function getData<T>(key: string): Promise<T> {
  // ...
}
```

## React

### Componentes

- Usar Server Components por defecto
- Client Components solo cuando sea necesario (uso de 'use client')
- Patrón de diseño: Container/Presentational
- Usa componentes funcionales con hooks
- Mantén los componentes pequeños y enfocados
- Extrae la lógica compleja a hooks personalizados

```typescript
const Button: React.FC<ButtonProps> = ({ children, onClick }) => {
  return (
    <button onClick={onClick}>
      {children}
    </button>
  );
};
```

### Props

- Define interfaces para props
- Usa tipos estrictos
- Documenta props complejas

```typescript
interface ButtonProps {
  variant: 'primary' | 'secondary';
  size?: 'sm' | 'md' | 'lg';
  onClick: () => void;
}
```

### Hooks

- Sigue las reglas de los hooks
- Extrae lógica reutilizable a hooks personalizados
- Usa nombres descriptivos

```typescript
const useWallet = () => {
  const [wallet, setWallet] = useState<Wallet | null>(null);
  // ...
};
```

## CSS/Tailwind

### Clases

- Usa clases de Tailwind de manera consistente
- Agrupa clases relacionadas
- Extrae patrones comunes a componentes

```tsx
<div className="flex items-center justify-between p-4 bg-white rounded-lg shadow">
  {/* ... */}
</div>
```

### Custom CSS

- Evita estilos inline
- Usa variables CSS para valores reutilizables
- Mantén la especificidad baja

```css
:root {
  --primary-color: #3b82f6;
  --spacing-unit: 1rem;
}
```

## Testing

### Estructura

- Coloca tests junto a los archivos que prueban
- Usa nombres descriptivos
- Sigue el patrón AAA (Arrange, Act, Assert)

```typescript
describe('Button', () => {
  it('should render correctly', () => {
    // Arrange
    const props = {};

    // Act
    render(<Button {...props} />);

    // Assert
    expect(screen.getByRole('button')).toBeInTheDocument();
  });
});
```

### Cobertura

- Mantén la cobertura por encima del 80%
- Enfócate en la lógica de negocio
- Prueba casos de error

## Documentación

### JSDoc

- Documenta funciones y componentes
- Incluye ejemplos de uso
- Especifica tipos de retorno

```typescript
/**
 * Hook para manejar la conexión de wallet
 * @returns {Object} Objeto con estado y métodos de wallet
 * @example
 * const { connect, disconnect } = useWallet();
 */
```

### Comentarios

- Escribe comentarios que expliquen el "por qué"
- Evita comentarios obvios
- Mantén los comentarios actualizados

## Git

### Commits

- Usa mensajes descriptivos
- Sigue el formato convencional
- Referencia issues cuando sea relevante

```
feat: add wallet connection
fix: resolve transaction signing issue
docs: update API documentation
```

### Branches

- Usa nombres descriptivos
- Sigue el patrón feature/fix/docs
- Mantén las ramas actualizadas

```
feature/wallet-integration
fix/transaction-error
docs/api-update
```

## Herramientas

### ESLint

- Sigue las reglas definidas en `.eslintrc`
- Corrige warnings antes de commit
- Usa `eslint-disable` con moderación

### Prettier

- Usa la configuración en `.prettierrc`
- Formatea el código antes de commit
- Mantén la consistencia en todo el proyecto

## Recursos

- [TypeScript Handbook](https://www.typescriptlang.org/docs/)
- [React Documentation](https://reactjs.org/docs)
- [Tailwind CSS](https://tailwindcss.com/docs)
- [Jest Documentation](https://jestjs.io/docs)

## Seguridad

- Validación de wallets con Solana-Web3 2.0
- CORS configurado con next.config.js
- Sanitización de inputs con DOMPurify