# 📱 Estilização Responsiva no React Native

Este documento apresenta estratégias e utilitários para tornar **interfaces adaptáveis** em diferentes dispositivos, resoluções e orientações no React Native.

---

## 🔍 1. Dimensões da Tela

Use o módulo `Dimensions` para obter largura e altura da tela.

```js
import { Dimensions } from 'react-native';

const { width, height } = Dimensions.get('window');
```

✅ Ideal para calcular larguras ou alturas relativas.

---

## 📐 2. Porcentagens com Flex

Prefira layouts baseados em `flex` para responsividade natural.

```jsx
<View style={{ flex: 1, justifyContent: 'center', paddingHorizontal: '10%' }}>
  <Text style={{ fontSize: 18, textAlign: 'center' }}>
    Layout adaptável!
  </Text>
</View>
```

✅ `padding`, `margin`, `width` e `height` aceitam strings com `%`.

---

## 🧠 3. `useWindowDimensions()` (hook recomendado)

Hook que retorna as dimensões da tela em tempo real, com suporte a rotação.

```js
import { useWindowDimensions } from 'react-native';

const { width, height } = useWindowDimensions();
```

✅ Reage a mudanças de orientação  
⚠️ Não funciona fora do React (ex: fora de componentes)

---

## 🧮 4. Escala por Densidade de Tela

Use `PixelRatio` ou bibliotecas para ajustar elementos a telas com diferentes densidades (DPI).

```js
import { PixelRatio } from 'react-native';

const scaledSize = PixelRatio.getFontScale() * 16;
```

---

## 🔧 5. Bibliotecas de Responsividade

### ✅ `react-native-responsive-screen`

```bash
npm install react-native-responsive-screen
```

```js
import { widthPercentageToDP as wp, heightPercentageToDP as hp } from 'react-native-responsive-screen';

<View style={{ width: wp('80%'), height: hp('10%') }} />
```

---

### ✅ `react-native-size-matters`

```bash
npm install react-native-size-matters
```

```js
import { scale, verticalScale, moderateScale } from 'react-native-size-matters';

<Text style={{ fontSize: moderateScale(16) }}>Texto escalável</Text>
```

---

## 🔄 6. Detecção de Orientação

```js
const isLandscape = width > height;
```

Ou com hook:

```js
useEffect(() => {
  const isLandscape = width > height;
  // Atualize layout...
}, [width, height]);
```

---

## 💡 7. Dicas Gerais

- Use `flex` sempre que possível (evite posições absolutas fixas)
- Combine porcentagens com `gap`, `padding`, `maxWidth`
- Teste em múltiplos tamanhos com Android Emulator e Expo Go
- Prefira `ScrollView` com `contentContainerStyle` para adaptar a altura
- Crie componentes que se ajustem com base no espaço, não no dispositivo

---

## 📚 Referências

- [Responsive Layout - React Native Docs](https://reactnative.dev/docs/layout-props)
- [react-native-size-matters](https://github.com/nirsky/react-native-size-matters)
- [Responsividade com Expo](https://docs.expo.dev/)

---

Este documento faz parte da seção [`react-native/styling`](./), onde documentamos técnicas de design adaptável e acessível para apps mobile.
