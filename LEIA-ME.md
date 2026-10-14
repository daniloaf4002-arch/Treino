# Treino Henderson – app Android

Projeto pronto para gerar o APK (app instalável no Android). O app funciona 100% offline:
o PDF e o backup são gerados no próprio celular e abrem o menu "Compartilhar" do Android
para você salvar (Drive, Arquivos, WhatsApp etc.).

## Opção 1 – Gerar o APK online, sem instalar nada (GitHub)
1. Crie uma conta gratuita em github.com e um repositório novo (pode ser privado).
2. Descompacte este ZIP e envie TODO o conteúdo para o repositório ("Add file" > "Upload files").
   Atenção: a pasta `.github` precisa subir junto. Se ela não aparecer após o envio, use
   "Add file" > "Create new file", digite o nome `.github/workflows/build-apk.yml` e cole nele o
   conteúdo do arquivo de mesmo nome deste projeto.
3. Abra a aba **Actions** > **Gerar APK** > **Run workflow**. Aguarde uns 5 a 10 minutos.
4. Entre na execução concluída, baixe o arquivo **treino-henderson-apk** (um ZIP) e extraia o
   `app-debug.apk`.
5. Envie o APK para o celular e instale (o Android vai pedir para permitir "instalar apps de
   fontes desconhecidas").

## Opção 2 – Pelo Android Studio (no computador)
Requer Node.js 20+, Java 17 e Android Studio.
```
npm install
npx cap add android
npx cap sync android
npx cap open android
```
No Android Studio: Build > Build Bundle(s) / APK(s) > Build APK(s).

## Observações
- Os registros ficam salvos no celular. Se desinstalar o app ou limpar os dados dele, o histórico
  se perde: use "Exportar backup" de tempos em tempos e "Importar backup" para restaurar.
- O arquivo `debug.keystore` mantém a assinatura do app sempre a mesma, então você pode instalar
  versões novas por cima sem perder os dados. Guarde este ZIP.
- O app usa o ícone padrão do Capacitor. O nome e o código do app estão em `capacitor.config.json`.
- O código do app está todo em `www/index.html`.
