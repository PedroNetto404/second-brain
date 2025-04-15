# 🚀 start_here.md — Guia Rápido: React Native no Ubuntu 22.04 (Android)

Este guia rápido mostra os passos essenciais para configurar o ambiente e iniciar um projeto React Native com foco exclusivo em desenvolvimento Android no Ubuntu 22.04.

---

## 📦 1. Instale as Dependências

### Node.js (v18+ recomendado)
```bash
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt install -y nodejs
```

### Yarn (alternativa ao npm)
```bash
npm install -g yarn
```

### Watchman (hot reload)
```bash
sudo apt install -y watchman
```

### Java JDK (necessário para Android SDK)
```bash
sudo apt install openjdk-17-jdk -y
```

---

## 📱 2. Configure o Android SDK

### Android Studio
1. Baixe e instale o [Android Studio](https://developer.android.com/studio).
2. Durante a instalação, certifique-se de instalar:
   - Android SDK
   - Android SDK Command-line Tools
   - Android Virtual Device (AVD)

### Configure variáveis de ambiente

Adicione ao seu `~/.zshrc` ou `~/.bashrc`:

```bash
export ANDROID_HOME=$HOME/Android/Sdk
export PATH=$ANDROID_HOME/emulator:$ANDROID_HOME/tools:$ANDROID_HOME/tools/bin:$ANDROID_HOME/platform-tools:$PATH
```

> Após adicionar, rode `source ~/.zshrc` ou `source ~/.bashrc`.

---

## ⚙️ 3. Instale o CLI do React Native

```bash
npm install -g react-native-cli
```

---

## 📁 4. Crie um Projeto

```bash
npx react-native init MeuApp
cd MeuApp
```

---

## ▶️ 5. Rode no Emulador Android

Certifique-se de que um AVD esteja rodando:

```bash
emulator -list-avds
emulator -avd NomeDoSeuAVD
```

Depois, execute:

```bash
npx react-native run-android
```

---

## 🧪 Verifique se Tudo Está Funcionando

Se tudo estiver OK, o app inicial do React Native será carregado no emulador.

---

## 🧰 Dicas

- Use `npx react-native doctor` para validar o setup.
- Reinicie o adb se necessário: `adb kill-server && adb start-server`
- Atalhos úteis com `yarn android` e `yarn start` (adicione scripts no `package.json`)

---

## 📚 Próximos Passos

- [intro/overview.md](react-native/intro/overview.md): O que é React Native?
- [intro/setup.md](react-native/intro/setup.md): Setup completo com detalhes
- [components/core.md](react-native/components/core.md): Primeiros componentes e estrutura JSX

---

> Este arquivo é parte da pasta `study/react-native/`, voltada para aprendizado prático e organizado de desenvolvimento mobile com React Native.
