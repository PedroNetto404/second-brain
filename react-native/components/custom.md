# 🧱 Componentes Customizados no React Native

Este documento aborda a criação de **componentes reutilizáveis**, organizados, testáveis e com propriedades flexíveis. Essa prática é essencial para escalar projetos com clareza e manutenibilidade.

---

## 📦 1. Por que criar componentes?

- Reduz duplicação de código
- Facilita manutenção e estilização
- Encapsula lógica visual ou funcional
- Ajuda na separação de responsabilidades (SRP)

---

## 🧑‍🎨 2. Exemplo Básico: `PrimaryButton`

```jsx
// components/PrimaryButton.js
import React from 'react';
import { TouchableOpacity, Text, StyleSheet } from 'react-native';

export default function PrimaryButton({ title, onPress }) {
  return (
    <TouchableOpacity style={styles.button} onPress={onPress}>
      <Text style={styles.label}>{title}</Text>
    </TouchableOpacity>
  );
}

const styles = StyleSheet.create({
  button: {
    backgroundColor: '#6200ee',
    padding: 12,
    borderRadius: 8,
    alignItems: 'center',
  },
  label: {
    color: '#fff',
    fontWeight: 'bold',
  },
});
```

Uso:

```jsx
<PrimaryButton title="Salvar" onPress={handleSalvar} />
```

---

## ⚙️ 3. Passagem de Props

Crie componentes que aceitem:

- `children`
- `style` customizável
- `...rest` (props extras nativos)

```jsx
export default function Card({ children, style, ...rest }) {
  return (
    <View style={[styles.card, style]} {...rest}>
      {children}
    </View>
  );
}
```

✅ Permite composição e extensibilidade.

---

## 🎯 4. Composição de Componentes

Combine múltiplos componentes para construir elementos mais ricos.

```jsx
function ProfileHeader({ user }) {
  return (
    <View style={styles.header}>
      <Image source={{ uri: user.avatar }} style={styles.avatar} />
      <Text style={styles.name}>{user.name}</Text>
    </View>
  );
}
```

---

## 🧱 5. Organização da Pasta `components/`

```bash
components/
├── Button/
│   ├── index.js
│   └── styles.js
├── Card/
│   └── index.js
├── ProfileHeader.js
└── ...
```

✅ Componentes complexos podem ter pasta própria com estilos, testes e hooks internos.

---

## 🧪 6. Testando Componentes

Use `@testing-library/react-native` para testes unitários:

```js
import { render, fireEvent } from '@testing-library/react-native';
import PrimaryButton from './PrimaryButton';

test('chama onPress ao clicar', () => {
  const fn = jest.fn();
  const { getByText } = render(<PrimaryButton title="OK" onPress={fn} />);
  fireEvent.press(getByText('OK'));
  expect(fn).toHaveBeenCalled();
});
```

---

## 🧠 Dicas

- Nomeie componentes com PascalCase
- Exporte apenas o necessário (evite `export default` em libs grandes)
- Documente props com `PropTypes` ou JSDoc (mesmo em TS opcionalmente)
- Prefira composição ao invés de herança visual
- Mantenha os componentes puros (sem lógica de dados interna)

---

## 📚 Referências

- [React Native - Custom Components](https://reactnative.dev/docs/components-and-apis)
- [Atomic Design aplicado a RN](https://bradfrost.com/blog/post/atomic-web-design/)
- [Testing Library - React Native](https://testing-library.com/docs/react-native-testing-library/intro/)

---

Este conteúdo faz parte da seção [`react-native/components`](./), e serve como base para componentização inteligente em apps escaláveis.
