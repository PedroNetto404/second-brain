# 📝 Formulários no React Native

Este documento aborda a criação de **formulários controlados** com `TextInput`, tratamento de entrada, validação básica e integração com bibliotecas de formulários.

---

## 🔡 1. Campo de Texto com Estado Controlado

```jsx
import React, { useState } from 'react';
import { View, TextInput, Text } from 'react-native';

export default function FormularioSimples() {
  const [nome, setNome] = useState('');

  return (
    <View>
      <Text>Nome:</Text>
      <TextInput
        value={nome}
        onChangeText={setNome}
        placeholder="Digite seu nome"
        style={{ borderBottomWidth: 1, marginBottom: 12 }}
      />
      <Text>Você digitou: {nome}</Text>
    </View>
  );
}
```

✅ Para múltiplos campos, use um `useState` por campo ou um objeto estado geral.

---

## 📋 2. Máscara de Entrada

Use bibliotecas como `react-native-masked-text` ou `react-native-text-input-mask`.

```bash
npm install react-native-masked-text
```

```jsx
import { TextInputMask } from 'react-native-masked-text';

<TextInputMask
  type={'cel-phone'}
  options={{ maskType: 'BRL' }}
  value={telefone}
  onChangeText={setTelefone}
/>
```

---

## ✅ 3. Validação Simples

```jsx
if (nome.trim().length < 3) {
  alert('Nome deve ter ao menos 3 letras');
}
```

Ou:

```jsx
<Text style={{ color: nome === '' ? 'red' : 'green' }}>
  {nome === '' ? 'Campo obrigatório' : '✓'}
</Text>
```

---

## 🧰 4. Validação com Bibliotecas

### react-hook-form

```bash
npm install react-hook-form
```

```jsx
import { useForm, Controller } from 'react-hook-form';

const { control, handleSubmit } = useForm();

<Controller
  control={control}
  name="email"
  rules={{ required: true }}
  render={({ field: { onChange, value } }) => (
    <TextInput placeholder="Email" onChangeText={onChange} value={value} />
  )}
/>
```

Chamada de envio:

```js
const onSubmit = data => console.log(data);
<Button onPress={handleSubmit(onSubmit)} title="Enviar" />
```

---

## 📌 5. Boas Práticas

- Use `autoCapitalize="none"` em emails e logins
- Use `keyboardType` correto (`email-address`, `numeric`, etc)
- Para senhas, adicione `secureTextEntry={true}`
- Combine com `KeyboardAvoidingView` e `ScrollView` para UX ideal
- Agrupe campos em componentes reutilizáveis (ex: `InputField`)

---

## 📚 Referências

- [React Native - TextInput](https://reactnative.dev/docs/textinput)
- [react-hook-form para React Native](https://react-hook-form.com/get-started#ReactNative)
- [Text Mask para RN](https://github.com/benhurott/react-native-masked-text)

---

Este conteúdo faz parte da seção [`react-native/components`](./), e serve como guia prático para construir formulários funcionais e reativos.
