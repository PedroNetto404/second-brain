# 🧩 Componentes Fundamentais do React Native

Este documento apresenta os principais **componentes nativos** que fazem parte do núcleo do React Native. São blocos básicos para criar qualquer layout ou funcionalidade.

---

## 📦 1. `View`

Elemento de contêiner, similar a `<div>` no HTML.

```jsx
import { View } from 'react-native';

<View style={{ padding: 20, backgroundColor: '#eee' }}>
  {/* Outros componentes aqui */}
</View>
```

✅ Usado para layout, agrupamento e posicionamento.

---

## 📝 2. `Text`

Renderiza texto na tela.

```jsx
import { Text } from 'react-native';

<Text style={{ fontSize: 16 }}>Olá, mundo!</Text>
```

✅ Suporta estilos como cor, tamanho, alinhamento, etc.

---

## 🔘 3. `Button`

Botão básico com título e ação `onPress`.

```jsx
import { Button } from 'react-native';

<Button title="Clique aqui" onPress={() => alert('Apertou!')} />
```

⚠️ Pouco personalizável — prefira `TouchableOpacity` para customização total.

---

## 🔘 4. `TouchableOpacity`

Componente touch com feedback visual de opacidade.

```jsx
import { TouchableOpacity, Text } from 'react-native';

<TouchableOpacity onPress={() => alert('Toque!')}>
  <Text>Pressione aqui</Text>
</TouchableOpacity>
```

✅ Ideal para botões customizados com `View` e `Text`.

---

## 🖼️ 5. `Image`

Exibe imagens locais ou remotas.

```jsx
import { Image } from 'react-native';

<Image
  source={{ uri: 'https://example.com/foto.png' }}
  style={{ width: 100, height: 100 }}
/>
```

✅ Use com largura/altura definidas.

---

## 🔄 6. `ScrollView`

Container com rolagem vertical (ou horizontal).

```jsx
import { ScrollView, Text } from 'react-native';

<ScrollView>
  <Text>Item 1</Text>
  <Text>Item 2</Text>
  {/* ... */}
</ScrollView>
```

⚠️ Para listas grandes, use `FlatList`.

---

## 📋 7. `FlatList`

Lista de alta performance para renderizar muitos itens.

```jsx
import { FlatList, Text } from 'react-native';

const dados = [{ id: '1', nome: 'Item A' }, { id: '2', nome: 'Item B' }];

<FlatList
  data={dados}
  keyExtractor={(item) => item.id}
  renderItem={({ item }) => <Text>{item.nome}</Text>}
/>
```

✅ Suporta lazy loading, otimização e headers personalizados.

---

## ⌨️ 8. `TextInput`

Campo de entrada de texto.

```jsx
import { TextInput } from 'react-native';

<TextInput
  placeholder="Digite seu nome"
  style={{ borderBottomWidth: 1 }}
/>
```

✅ Use `value` e `onChangeText` para controle total.

---

## 📌 Outros Componentes Úteis

| Componente       | Função                         |
|------------------|--------------------------------|
| `SafeAreaView`   | Evita sobreposição em notch    |
| `KeyboardAvoidingView` | Move tela ao abrir teclado |
| `Modal`          | Exibe conteúdo sobreposto      |
| `ActivityIndicator` | Mostra loading               |
| `Pressable`      | Alternativa a `Touchable*`     |

---

## 📚 Referência Oficial

- [React Native Components](https://reactnative.dev/docs/components-and-apis)
- [React Native Style Guide](https://reactnative.dev/docs/style)

---

Este documento faz parte de [`react-native/components`](./), e cobre os blocos básicos para construção de UIs com React Native.
