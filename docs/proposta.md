# Proposta do lucerna-phone

O `lucerna-phone` gerencia celulares a partir do desktop.

- **Espelhamento e controle:** pelo [scrcpy](https://github.com/Genymobile/scrcpy).
- **Demais funções:** recria em Rust as outras funções do KDE Connect, com um protocolo próprio e um app próprio no celular, o [`lucerna-phone-android`](https://github.com/EduardoSA8006/lucerna-phone-android).
- **Uso:** funciona sozinho, com uma TUI. Com o Lucerna, ganha um painel.

Segue a estrutura de apps do [ecossistema](https://github.com/EduardoSA8006/lucerna-sdk/blob/main/docs/ecossistema.md): núcleo, serviço, TUI e painel em QML.

## Painel e TUI

O painel serve para olhar e agir rápido. O trabalho completo fica na TUI.

**No painel:**

- o aparelho: bateria, sinal e se está conectado;
- ações de um clique: espelhar a tela pelo scrcpy, enviar um arquivo, tocar o celular para achá-lo e copiar a área de transferência;
- as notificações do celular nas notificações do shell, com resposta a mensagens.

**Só na TUI:**

- parear;
- escolher o que sincronizar;
- navegar pelos arquivos do celular;
- permissões.

## Em aberto

- Quais funções do KDE Connect entram primeiro.
- A descoberta e o pareamento.
- A segurança e a criptografia.
- Android só ou também iOS.
- Como a conexão com o celular fica ouvindo. O celular precisa achar o computador e mandar notificações, então alguém tem que estar ouvindo a porta, e o serviço sob demanda do [ecossistema](https://github.com/EduardoSA8006/lucerna-sdk/blob/main/docs/ecossistema.md) não cobre isso sozinho. Duas opções, sem decisão ainda:
  - **Ativação por socket de rede do systemd:** o systemd ouve a porta e sobe o serviço quando o celular conecta. O serviço continua sob demanda.
  - **Serviço sempre ligado só enquanto houver aparelho pareado:** sem aparelho pareado, ele volta a ser sob demanda.
