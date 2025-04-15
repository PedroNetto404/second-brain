# 🧭 Navegação com React Navigation

Este documento apresenta a configuração, conceitos e exemplos práticos com a biblioteca **React Navigation**, a solução mais utilizada para navegação em aplicações React Native.

---

## 📦 1. Instalação da Biblioteca

```bash
npm install @react-navigation/native
```

Dependências adicionais:

```bash
# Expo:
npx expo install react-native-screens react-native-safe-area-context react-native-gesture-handler react-native-reanimated

# Bare React Native:
npm install react-native-screens react-native-safe-area-context react-native-gesture-handler react-native-reanimated
```

Instale também os stacks/tabs se necessário:

```bash
npm install @react-navigation/native-stack
npm install @react-navigation/bottom-tabs
```

---

## 🧱 2. Estrutura Básica com Native Stack

```jsx
import { NavigationContainer } from '@react-navigation/native';
import { createNativeStackNavigator } from '@react-navigation/native-stack';
import Home from './screens/Home';
import Detalhes from './screens/Detalhes';

const Stack = createNativeStackNavigator();

export default function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator>
        <Stack.Screen name="Home" component={Home} />
        <Stack.Screen name="Detalhes" component={Detalhes} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}
```

---

## 🔁 3. Navegar entre Telas

```js
// Dentro de Home.js
navigation.navigate('Detalhes', { id: 42 });
```

Receber params:

```js
// Dentro de Detalhes.js
const route = useRoute();
const { id } = route.params;
```

---

## 🔙 4. Voltar para a tela anterior

```js
navigation.goBack();
```

---

## 📐 5. Tipos de Navegador

| Tipo                  | Pacote                             | Uso típico                      |
|-----------------------|------------------------------------|----------------------------------|
| Stack Navigator       | `@react-navigation/native-stack`   | Navegação hierárquica (push/pop) |
| Bottom Tabs           | `@react-navigation/bottom-tabs`    | Menus inferiores                 |
| Drawer Navigator      | `@react-navigation/drawer`         | Menus laterais (hambúrguer)     |
| Material Top Tabs     | `@react-navigation/material-top-tabs` | Swipes horizontais estilo Android |

---

## 🎨 6. Customizações Comuns

### Remover header

```jsx
<Stack.Screen name="Home" component={Home} options={{ headerShown: false }} />
```

### Alterar título dinamicamente

```js
navigation.setOptions({ title: 'Novo título' });
```

---

## 📁 7. Organização recomendada de rotas

```bash
src/
├── navigation/
│   ├── AppNavigator.js
│   └── AuthNavigator.js
├── screens/
│   ├── Home.js
│   ├── Detalhes.js
│   └── Login.js
```

---

## 📚 Referências

- [Documentação oficial](https://reactnavigation.org/docs/getting-started/)
- [Native Stack (melhor performance)](https://reactnavigation.org/docs/native-stack-navigator)
- [Expo + Navigation](https://docs.expo.dev/guides/routing/)

---

Este arquivo faz parte da seção [`react-native/navigation`](./), e serve como base para implementar navegação com pilhas, abas e drawers em apps mobile.
