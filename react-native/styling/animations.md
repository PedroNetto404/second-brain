# 🎞️ Animações no React Native

Este documento apresenta os principais recursos e bibliotecas para criar animações fluidas e responsivas no React Native. Animações são essenciais para **UX moderna**, transições suaves e feedback visual.

---

## 🎛️ 1. Animated API (Básica)

```jsx
import React, { useRef, useEffect } from 'react';
import { Animated, View } from 'react-native';

export default function FadeInBox() {
  const fadeAnim = useRef(new Animated.Value(0)).current;

  useEffect(() => {
    Animated.timing(fadeAnim, {
      toValue: 1,
      duration: 500,
      useNativeDriver: true,
    }).start();
  }, []);

  return <Animated.View style={{ opacity: fadeAnim, width: 100, height: 100, backgroundColor: 'blue' }} />;
}
```

✅ Use `useRef` para instanciar valores animados  
✅ `useNativeDriver: true` para melhor performance

---

## 🔄 2. LayoutAnimation (auto-animação)

Anima automaticamente alterações de layout (ex: inserções, remoções).

```js
import { LayoutAnimation } from 'react-native';

LayoutAnimation.configureNext(LayoutAnimation.Presets.easeInEaseOut);
```

⚠️ No Android, ative com:

```js
import { UIManager, Platform } from 'react-native';

if (Platform.OS === 'android') {
  UIManager.setLayoutAnimationEnabledExperimental &&
    UIManager.setLayoutAnimationEnabledExperimental(true);
}
```

---

## ✨ 3. Animando com `Animated.ValueXY` (posições)

```jsx
const pos = useRef(new Animated.ValueXY({ x: 0, y: 0 })).current;

Animated.spring(pos, {
  toValue: { x: 100, y: 100 },
  useNativeDriver: false,
}).start();
```

✅ Ideal para drag & drop, movimentos suaves

---

## 🚀 4. react-native-reanimated (avançado)

```bash
npm install react-native-reanimated
```

- Melhor desempenho
- Suporte a gestos (via `react-native-gesture-handler`)
- Base para bibliotecas como `Moti`, `GestureHandler`, `FlashList`

```js
import Animated, { useSharedValue, useAnimatedStyle, withSpring } from 'react-native-reanimated';

const offset = useSharedValue(0);

const animatedStyles = useAnimatedStyle(() => ({
  transform: [{ translateX: withSpring(offset.value) }],
}));
```

✅ Use com `react-native-gesture-handler` para experiências avançadas

---

## 🎥 5. Libs e Helpers Populares

| Biblioteca           | Uso principal                         |
|----------------------|----------------------------------------|
| `react-native-reanimated` | Animações performáticas + gestos    |
| `react-native-animatable`| Animações prontas e declarativas    |
| `moti`               | Animações simples com API de alto nível |
| `framer-motion`      | (Web) Referência para API declarativa  |

---

## ⚡ Dicas Rápidas

- Prefira `useNativeDriver: true` (exceto se animar layout/cores)
- Use `Animated.View`, `Animated.Text`, `Animated.ScrollView`
- Combine `delay`, `loop`, `sequence` e `parallel` para efeitos complexos
- Evite re-renders desnecessários em componentes animados
- Use `LayoutAnimation` para ações de visibilidade (como toggle, collapse)

---

## 📚 Referências

- [Animated Docs (React Native)](https://reactnative.dev/docs/animated)
- [react-native-reanimated](https://docs.swmansion.com/react-native-reanimated/)
- [LayoutAnimation Guide](https://reactnative.dev/docs/layoutanimation)
- [Moti Library](https://moti.fyi/)

---

Este arquivo faz parte da seção [`react-native/styling`](./), e serve como referência para criar interações visuais fluídas e modernas.
