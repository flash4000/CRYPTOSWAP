# Utilidades Comunes

## Organización de Utilidades

### 1. Utilidades de Blockchain (`/utils/blockchain/`)
- Funciones para interactuar con la blockchain
- Helpers para transacciones
- Utilidades para wallets

### 2. Utilidades de Formato (`/utils/format/`)
- Formateo de números
- Formateo de fechas
- Formateo de direcciones

### 3. Utilidades de Validación (`/utils/validation/`)
- Validación de inputs
- Validación de transacciones
- Validación de wallets

### 4. Utilidades de API (`/utils/api/`)
- Funciones para llamadas a API
- Manejo de errores
- Transformación de datos

### 5. Utilidades de UI (`/utils/ui/`)
- Funciones para animaciones
- Helpers para estilos
- Utilidades para temas

## Convenciones
- Usar nombres descriptivos y en camelCase
- Agregar tipos TypeScript
- Documentar parámetros y retornos
- Mantener funciones puras cuando sea posible
- Agregar pruebas unitarias

## Ejemplo de Estructura
```typescript
// utils/format/currency.ts
export const formatCurrency = (amount: number, currency: string): string => {
  // Implementación
};

// utils/validation/transaction.ts
export const validateTransaction = (tx: Transaction): ValidationResult => {
  // Implementación
};
``` 