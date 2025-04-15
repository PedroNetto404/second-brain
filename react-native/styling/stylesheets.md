# 🎨 Estilização com StyleSheet no React Native

Este documento aborda a estilização de componentes utilizando o sistema nativo do React Native com `StyleSheet`, incluindo práticas recomendadas e formas de composição de estilos reutilizáveis.

---

## 🧱 1. Estilos com `StyleSheet.create`

```jsx
import { StyleSheet, View } from 'react-native';

const styles = StyleSheet.create({
  container: {
    backgroundColor: '#f0f0f0',
    padding: 16,
    borderRadius: 8,
  },
});

<View style={styles.container} />
```

✅ `StyleSheet.create` ajuda na validação e otimização dos estilos.

---

## ✏️ 2. Estilos Inline (não recomendado)

```jsx
<View style={{ backgroundColor: 'red', padding: 10 }} />
```

⚠️ Menos performático e difícil de manter.

---

## 🧬 3. Composição de Estilos

Combine múltiplos estilos com array:

```jsx
<View style={[styles.base, styles.card, isAtivo && styles.ativo]} />
```

✅ Ordem importa: o último estilo sobrescreve os anteriores.

---

## 🎛️ 4. Props Condicionais

```jsx
const styles = StyleSheet.create({
  botao: {
    backgroundColor: '#eee',
  },
  ativo: {
    backgroundColor: '#00f',
  },
});

<TouchableOpacity style={[styles.botao, ativo && styles.ativo]} />
```

✅ Ajuda a alternar temas, estados ou modos escuros.

---

## 🧠 5. Estilos em Arquivos Separados

```bash
components/
├── MeuCard.js
├── MeuCard.styles.js
```

```js
// MeuCard.styles.js
import { StyleSheet } from 'react-native';

export default StyleSheet.create({
  container: {
    backgroundColor: '#fff',
    padding: 16,
    borderRadius: 10,
  },
});
```

✅ Melhora a legibilidade e reutilização.

---

## 🧪 6. Boas Práticas

- Use nomes consistentes (`container`, `label`, `button`, `card`)
- Agrupe estilos visuais vs estruturais se necessário
- Crie um `theme.js` para cores e fontes globais
- Evite `marginTop` em cascata — prefira `gap` com `flex` onde possível
- Prefira `StyleSheet.create` para produção

---

## 🌐 7. Utilitários e Bibliotecas Úteis

- `react-native-extended-stylesheet`: suporte a variáveis
- `tailwind-rn`: utilitário inspirado no Tailwind CSS
- `styled-components/native`: alternativa com template literals (ver `css-in-js`)

---

## 📚 Referências

- [Documentação Oficial - StyleSheet](https://reactnative.dev/docs/stylesheet)
- [Guia de Tematização com RN](https://callstack.com/blog/theming-in-react-native)
- [Tailwind para RN (tailwind-rn)](https://github.com/vadimdemedes/tailwind-rn)

---

Este documento faz parte da seção [`react-native/styling`](./), onde exploramos abordagens escaláveis e eficientes para estilizar apps mobile.
