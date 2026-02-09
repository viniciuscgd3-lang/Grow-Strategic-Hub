# Grow Strategic Hub (Android via Capacitor)

Este projeto empacota o painel web existente dentro de um app Android usando Capacitor, mantendo o HTML/CSS/JS original intacto.

## Estrutura de pastas

```
.
├── capacitor.config.json
├── package.json
├── README.md
└── www
    └── index.html
```

## Pré-requisitos

- Node.js 18+ e npm
- Android Studio (com Android SDK instalado)
- Java JDK 17

## Como rodar localmente no Android

1. Instale as dependências:
   ```bash
   npm install
   ```

2. Gere o projeto Android (apenas na primeira vez):
   ```bash
   npx cap add android
   ```

3. Sincronize os assets web com o Android:
   ```bash
   npx cap sync
   ```

4. Abra o projeto no Android Studio:
   ```bash
   npx cap open android
   ```

5. No Android Studio, clique em **Run** para instalar no emulador ou dispositivo.

## Gerar APK (release)

1. Abra o projeto Android:
   ```bash
   npx cap open android
   ```
2. No Android Studio, vá em **Build > Generate Signed Bundle / APK**.
3. Escolha **APK**, selecione ou crie um keystore e finalize a geração.
4. O APK será gerado na pasta indicada pelo Android Studio.

## Observações

- O app utiliza `localStorage` dentro do WebView do Android, mantendo o comportamento atual de persistência local.
- Para integração com APIs externas (Gemini), certifique-se de inserir a chave no campo `apiKey` dentro de `www/index.html` ou implementar uma injeção segura em runtime.
