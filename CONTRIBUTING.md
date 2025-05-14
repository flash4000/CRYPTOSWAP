# Guía de Contribución

¡Gracias por tu interés en contribuir a CryptoSwap! Este documento proporciona las pautas y el proceso para contribuir al proyecto.

## 🎯 Proceso de Contribución

1. **Fork y Clone**
   ```bash
   git clone https://github.com/tu-usuario/cryptoswap.git
   cd cryptoswap
   ```

2. **Configuración del Entorno**
   ```bash
   npm install
   cp .env.example .env
   ```

3. **Crear Rama**
   ```bash
   git checkout -b feature/nombre-feature
   ```

4. **Desarrollo**
   - Sigue las convenciones de código
   - Escribe tests para nuevas funcionalidades
   - Actualiza la documentación

5. **Commits**
   - Usa mensajes descriptivos
   - Sigue el formato: `tipo(alcance): descripción`
   - Ejemplo: `feat(wallet): add Phantom wallet support`

6. **Pull Request**
   - Describe los cambios
   - Incluye capturas si es necesario
   - Referencia issues relacionados

## 📝 Convenciones de Código

- **TypeScript**: Usa tipos estrictos
- **React**: Componentes funcionales con hooks
- **Testing**: Jest + React Testing Library
- **Estilo**: ESLint + Prettier

## 🧪 Testing

```bash
# Tests unitarios
npm test

# Tests E2E
npm run test:e2e

# Coverage
npm run test:coverage
```

## 📚 Documentación

- Documenta nuevas funcionalidades
- Actualiza README si es necesario
- Incluye ejemplos de uso

## 🔍 Code Review

- Revisa el código antes de PR
- Asegura que los tests pasen
- Verifica el formato del código

## 🚀 Despliegue

- Verifica que funcione en desarrollo
- Prueba en staging si es posible
- Sigue la guía de despliegue

## Código de Conducta

Al contribuir a este proyecto, aceptas mantener un ambiente respetuoso y profesional. Por favor, lee nuestro [Código de Conducta](CODE_OF_CONDUCT.md) antes de contribuir.

## ¿Cómo Contribuir?

1. Haz un fork del repositorio
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Haz commit de tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## Proceso de Desarrollo

1. **Configuración del Entorno**
   ```bash
   # Clonar el repositorio
   git clone https://github.com/tu-usuario/cryptoswap.git
   cd cryptoswap

   # Instalar dependencias
   npm install

   # Iniciar el servidor de desarrollo
   npm run dev
   ```

2. **Flujo de Trabajo**
   - Crea una rama desde `main`
   - Desarrolla tu feature
   - Asegúrate de que las pruebas pasen
   - Actualiza la documentación si es necesario
   - Crea un Pull Request

## Estándares de Código

- Usa TypeScript para todo el código nuevo
- Sigue las convenciones de estilo definidas en `.eslintrc` y `.prettierrc`
- Escribe código limpio y mantenible
- Documenta funciones y componentes con JSDoc
- Mantén los componentes pequeños y enfocados

## Pruebas

- Escribe pruebas unitarias para nuevas funcionalidades
- Asegúrate de que todas las pruebas pasen antes de hacer commit
- Mantén la cobertura de pruebas por encima del 80%

```bash
# Ejecutar pruebas
npm test

# Ejecutar pruebas con cobertura
npm run test:coverage
```

## Documentación

- Actualiza la documentación relevante
- Incluye ejemplos de uso
- Documenta cambios importantes en el API
- Mantén el README actualizado

## Revisión de Código

1. **Antes de Enviar un PR**
   - Asegúrate de que tu código sigue los estándares
   - Ejecuta todas las pruebas
   - Actualiza la documentación
   - Revisa tu propio código

2. **Proceso de Revisión**
   - Los PRs serán revisados por al menos un mantenedor
   - Los comentarios deben ser constructivos y respetuosos
   - Responde a los comentarios de revisión
   - Haz los cambios necesarios

3. **Después de la Aprobación**
   - Los commits serán squash antes de mergear
   - El PR será mergeado por un mantenedor
   - La rama será eliminada después del merge

## Contacto

Si tienes preguntas o necesitas ayuda, por favor:
- Abre un issue
- Contacta a los mantenedores
- Únete a nuestro canal de Discord

¡Gracias por contribuir a hacer CryptoSwap mejor! 