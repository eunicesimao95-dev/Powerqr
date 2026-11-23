# PowerQR — aplicação Flutter para Android

**Criadora:** Eunice Simão  
**Versão:** 1.0.1 — protótipo interativo

## O que já funciona nesta versão
- Interface PowerQR e navegação entre Início, Pedir, Partilhar e Perfil.
- Formulário com validação da percentagem pretendida.
- QR Code pessoal gerado com o nome e a percentagem escolhida.
- Leitura de QR Code através da câmara.
- Opção local para indicar disponibilidade.
- Edição do nome apresentado no perfil.

## O que ainda não é uma rede real
Os pedidos e a disponibilidade existem apenas dentro desta demonstração. Ainda não há contas, servidor, base de dados, localização, descoberta de pessoas próximas, notificações nem sincronização entre telemóveis. O nível da bateria não é lido pelo aparelho nesta versão.

**Limite físico essencial:** QR Code e Bluetooth não transportam energia elétrica. Para carregar um telemóvel a partir de outro, os aparelhos precisam de suportar carregamento reverso compatível, por cabo ou sem fios. A aplicação pode coordenar e identificar utilizadores, mas não cria essa capacidade no hardware.

## Gerar o instalador Android (APK) sem computador
O ficheiro `.github/workflows/build-apk.yml` prepara uma compilação na nuvem com GitHub Actions.

1. Extrai o ZIP do projeto.
2. Cria um repositório chamado `PowerQR` em https://github.com/.
3. Envia para o repositório todos os ficheiros e pastas do projeto, incluindo a pasta oculta `.github/workflows`.
4. Faz Commit.
5. Abre **Actions** e escolhe a execução **Build PowerQR Android APK**.
6. Quando terminar com sucesso, abre a execução e descarrega o artefacto **PowerQR-Android-APK**.
7. Extrai o ZIP do artefacto e instala `app-release.apk` no Android.

Se o site móvel não permitir enviar a pasta oculta `.github`, será preciso ativar a visualização de ficheiros ocultos ou usar um método de envio que preserve essa pasta.

## Compilar localmente
Com Flutter instalado:
```bash
flutter create . --platforms=android --org com.eunicesimao
flutter pub get
flutter analyze
flutter build apk --release
```
O APK aparece em `build/app/outputs/flutter-apk/app-release.apk`.

Esta versão ainda precisa de testes num Android real. Não é uma versão pronta para publicação pública.
