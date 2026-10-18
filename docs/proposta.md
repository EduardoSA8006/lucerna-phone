# Proposta do lucerna-phone

O `lucerna-phone` gerencia celulares a partir do desktop.

- **Espelhamento e controle:** pelo [scrcpy](https://github.com/Genymobile/scrcpy).
- **Demais funções:** recria em Rust as outras funções do KDE Connect, com um protocolo próprio e um app próprio no celular, o [`lucerna-phone-android`](https://github.com/EduardoSA8006/lucerna-phone-android).
- **Uso:** funciona sozinho, com uma TUI. Com o Lucerna, ganha um painel.

Segue a estrutura de apps do [ecossistema](https://github.com/EduardoSA8006/lucerna-sdk/blob/main/docs/ecossistema.md): núcleo, TUI, provedor e painel em QML.

## Em aberto

- Quais funções do KDE Connect entram primeiro.
- A descoberta e o pareamento.
- A segurança e a criptografia.
- Android só ou também iOS.
