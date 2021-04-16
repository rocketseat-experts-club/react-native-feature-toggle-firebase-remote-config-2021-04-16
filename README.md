# react-native-feature-toggle-with-firebase

<img src="https://storage.googleapis.com/golden-wind/experts-club/capa-github.svg" />

## Expert

| [<img src="https://avatars.githubusercontent.com/u/6079947?s=460&u=d7af98379f7769fc782b4e99d86a205c44e57f79&v=4" width="75px;"/>](https://github.com/hstrada) |
| :-: |
|[Helena Strada](https://github.com/hstrada)|

### título: Utilizando feature toggle no React Native com Firebase Remote Config
### tags: react native, feature toggle, feature flag, firebase
### descrição: neste desafio iremos utilizar os conceitos de feature toggle aplicados ao desenvolvimento mobile, no universo do react native, utilizando o firebase remote config como ferramenta


## Create Project

```bash
npx react-native init Remotine --template react-native-template-typescript
```

---

### Exemplo na prática

```jsx
const App = () => {
  const isFeatureEnabled = true;

  return (
    <View>
      {isFeatureEnabled ? <Text>Caminho A</Text> : <Text>Caminho Antigo</Text>}
    </View>
  );
};
```

## Firebase Support

```bash
yarn add @react-native-firebase/app
```

## Remote Config Support

```bash
yarn add @react-native-firebase/remote-config
```

---

### Android Setup

Firebase console -> download google-services.json and place it at:
```bash
/android/app/google-services.json
```

> https://developers.google.com/android/guides/google-services-plugin

/android/build.gradle

```java
buildscript {
  dependencies {
    // ... other dependencies
    classpath 'com.google.gms:google-services:4.3.4'
    // Add me --- /\
  }
}
```

/android/app/build.gradle

```java
apply plugin: 'com.android.application'
apply plugin: 'com.google.gms.google-services' // <- Add this line
```

### iOS Setup

```bash
cd ios && pod install
```

Download GoogleService-Info.plist from firebase console

Copy them to project

```bash
cd ios && open Remotine.xcworkspace
```

Add GoogleService-Info.plist to project and check 'copy items if needed' box

/ios/Remotine/AppDelegate.m

```swift
#import <Firebase.h>
```

Inside *didFinishLaunchingWithOptions* method

```swift
if ([FIRApp defaultApp] == nil) {
  [FIRApp configure];
}
```

---

### Amostragem, liberar por condicional

### pontos de atenção

git flow

estrutura default

tratamentos de erro - internet

gerou métricas?
vai precisar desligar de forma tranquila?

até que ponto vale a pena trazer?
precisa gerenciar muita coisa dentro do app
troca de bff, layout

### Referências

https://firebase.google.com/docs/remote-config/loading