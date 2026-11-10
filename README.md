# Nestopia Launcher

[![Release](https://img.shields.io/github/v/release/keuyn/NestopiaLauncher?style=flat-square)](https://github.com/keuyn/NestopiaLauncher/releases/latest)
[![Licença: MIT](https://img.shields.io/badge/licen%C3%A7a-MIT-green?style=flat-square)](https://github.com/keuyn/NestopiaLauncher/blob/main/LICENSE)
[![Plataforma](https://img.shields.io/badge/plataforma-Windows%2010%2F11-blue?style=flat-square)]()

Launcher visual para o emulador **Nestopia JG**, com grade de capas, busca em tempo real, favoritos, jogos recentes, filtros, fundo dinâmico, efeitos sonoros e suporte a controles XInput e DirectInput.

> **Download rápido:** baixe a versão mais recente na página de [Releases](https://github.com/keuyn/NestopiaLauncher/releases/latest).

## Índice

- [Sobre o projeto](#sobre-o-projeto)
- [Recursos](#recursos)
- [Requisitos](#requisitos)
- [Download e instalação](#download-e-instalação)
- [Primeira configuração](#primeira-configuração)
- [Como usar](#como-usar)
- [Controles](#controles)
- [Capas](#capas)
- [Onde ficam os dados](#onde-ficam-os-dados)
- [Solução de problemas](#solução-de-problemas)
- [Perguntas frequentes](#perguntas-frequentes)
- [Licença](#licença)
- [Créditos](#créditos)
- [Links úteis](#links-úteis)

## Sobre o projeto

O **Nestopia Launcher** é uma interface para o emulador **Nestopia JG**. Ele organiza sua biblioteca de ROMs de NES em uma grade visual, permite pesquisar jogos, marcar favoritos, acessar os jogos recentes e iniciar tudo pelo teclado ou pelo controle.

O pacote disponibilizado na página de Releases já inclui o Nestopia JG. As ROMs **não** são incluídas.

## Recursos

- Grade de jogos com capas e cartucho de fallback para jogos sem capa
- Busca em tempo real pelo nome do jogo
- Favoritos com estrela no card
- Lista de jogos recentes com limite configurável
- Filtros: Todos, Favoritos e Recentes
- Fundo dinâmico desfocado com a capa do jogo selecionado
- Efeitos sonoros de navegação e seleção (podem ser desativados)
- Configurações persistentes entre execuções
- Remapeamento dos botões do controle
- Suporte a controles XInput (Xbox 360/One/Series)
- Suporte a controles DirectInput (DualShock/PS2 via adaptador USB e genéricos)
- Analógico esquerdo para navegar, com zona morta configurável
- Janela Sobre com versão, links do autor e link para download de ROMs

## Requisitos

- Windows 10 ou Windows 11 (64 bits)
- Não é necessário instalar o .NET
- O pacote do release já inclui o emulador Nestopia JG
- ROMs de NES não são incluídas
- Um controle é opcional; teclado e mouse funcionam normalmente

## Download e instalação

1. Acesse a página de [Releases](https://github.com/keuyn/NestopiaLauncher/releases/latest).
2. Baixe o pacote mais recente (`.zip`).
3. Extraia o conteúdo em uma pasta de sua preferência, por exemplo `C:\NestopiaLauncher`.
4. Execute `NestopiaLauncher.exe`.
5. Se o Windows exibir o aviso do SmartScreen, clique em **Mais informações** e depois em **Executar assim mesmo**.

O launcher é portátil: não precisa de instalador. As configurações e os favoritos ficam salvos na pasta do usuário, então atualizar ou mover o executável não apaga seus dados.

O pacote já traz o Nestopia JG. Se você já possui outra instalação do emulador, também pode apontar para ela na primeira configuração.

## Primeira configuração

Na primeira execução, pressione **F2** ou o botão **Select/Back** do controle para abrir a janela **Configurações**.

Preencha os campos:

- **Nestopia (.exe):** selecione o `nestopia.exe` que veio junto no pacote ou a sua instalação existente.
- **Pasta de ROMs:** selecione a pasta onde estão ou serão colocadas as ROMs. Crie uma pasta se ainda não tiver.
- **Pasta de capas:** selecione uma pasta para as capas. Pode ser uma pasta vazia; o launcher cria e organiza os arquivos.
- **Extensões aceitas:** por padrão `.nes, .zip, .fds`. Adicione outras extensões se precisar, separadas por vírgula.
- **Máx. recentes:** quantidade de jogos exibidos no filtro Recentes (1 a 100).
- **Efeitos sonoros:** ativa ou desativa os sons de navegação e seleção.
- **Fundo dinâmico:** ativa ou desativa o fundo desfocado com a capa do jogo selecionado.

Clique em **Salvar**. Depois, coloque suas ROMs na pasta configurada e volte para a tela principal.

> Se a pasta de capas estiver vazia, o launcher tenta baixar as capas automaticamente. Jogos sem capa usam o cartucho padrão **SEM CAPA**.

## Como usar

### Tela principal

- **MEUS JOGOS NES:** título e contador de jogos encontrados.
- **Badge de filtro:** mostra o filtro atual: TODOS, FAVORITOS ou RECENTES.
- **Busca:** digite para filtrar os jogos em tempo real. O botão **✕** limpa a busca. A tecla **Esc** também limpa o texto quando a busca está focada.
- **Grade de jogos:** use as setas, o D-Pad ou o analógico esquerdo para navegar. Pressione **Enter** ou **A** para abrir o jogo. Também é possível dar um duplo clique com o mouse.
- **Estrela:** indica que o jogo está nos favoritos.
- **SOBRE:** abre a janela com versão, links do autor e link para download de ROMs.
- **Rodapé:** mostra um resumo dos atalhos disponíveis.

### Busca

- Digite qualquer parte do nome do jogo para filtrar a lista.
- Pressione **Seta para baixo** para ir da busca para a grade.
- Pressione **Esc** para limpar a busca.
- O contador mostra quantos jogos foram encontrados.

### Favoritos

- Selecione um jogo e pressione **F** no teclado ou **X** no controle (mapeamento padrão).
- Uma estrela aparece no card do jogo.
- Use o filtro **Favoritos** para exibir apenas os jogos marcados.

### Jogos recentes

- Um jogo entra na lista de recentes automaticamente quando é aberto.
- Use o filtro **Recentes** para ver os últimos jogos abertos.
- O limite de itens pode ser alterado nas configurações.

### Filtros

Pressione **Y** no teclado ou no controle para alternar entre:

1. **Todos**
2. **Favoritos**
3. **Recentes**

O badge ao lado do título mostra o filtro ativo.

### Fundo dinâmico

Quando ativado, a capa do jogo selecionado aparece desfocada no fundo da tela. Para desativar, abra as configurações e desmarque **Fundo dinâmico com a capa do jogo selecionado**.

### Efeitos sonoros

O launcher toca sons suaves ao navegar e selecionar jogos. Para desativar, abra as configurações e desmarque **Efeitos sonoros de navegação e seleção**.

### Janela Sobre

Abra com **F1** ou com o botão **SOBRE**. A janela mostra:

- Versão do launcher
- Autor do projeto
- Link do GitHub
- Link do Instagram
- Link para download de ROMs de NES, caso você ainda não tenha os jogos

### Sair

Pressione **Esc** na tela principal para fechar o launcher. Se um jogo estiver aberto, feche o jogo primeiro ou use o atalho de encerrar jogo.

## Controles

### Teclado

| Tecla | Ação |
| --- | --- |
| Setas | Navegar pela grade |
| Enter | Abrir o jogo selecionado |
| Esc | Sair do launcher |
| F | Favoritar ou desfavoritar o jogo selecionado |
| Y | Alternar filtro (Todos → Favoritos → Recentes) |
| F1 | Abrir a janela Sobre |
| F2 | Abrir as configurações |
| Digitar | Pesquisar jogos |
| Seta para baixo (na busca) | Ir para a grade |

### Controle (padrões XInput)

| Botão | Ação |
| --- | --- |
| D-Pad | Navegar pela grade |
| Analógico esquerdo | Navegar pela grade |
| A | Abrir o jogo selecionado |
| X | Favoritar ou desfavoritar |
| Y | Alternar filtro |
| Back / Select | Abrir as configurações |
| Start + Back | Encerrar o jogo em execução |

> Os botões acima são os padrões para controles XInput. Todos podem ser remapeados em **Configurações → Controle**.

### Controles DirectInput (DualShock/PS2)

Controles DualShock, PS2 e vários modelos genéricos são reconhecidos via DirectInput. Como a numeração dos botões varia conforme o adaptador, eles aparecem na captura como **Botão 1**, **Botão 2**, etc.

Na primeira vez que usar um controle DirectInput, remapeie as ações:

1. Conecte o controle antes de abrir as configurações.
2. Abra **Configurações → Controle**.
3. Clique na ação que deseja remapear: Jogar, Favoritar, Filtro, Configurações ou Encerrar jogo.
4. O botão começa a piscar. Pressione o botão desejado no controle.
5. O novo mapeamento é aplicado na hora. Clique em **Salvar** para manter.

### Remapeamento do controle

- Clique em uma ação e pressione o botão desejado no controle.
- Pressione **Delete** para definir a ação como **Nenhum** (desativa a ação).
- Pressione **Esc** ou **Enter** para cancelar a captura.
- O **D-Pad** é reservado para navegação e não pode ser usado como ação.
- Combinações, como **Start + Back**, são capturadas quando os botões são pressionados juntos.
- O launcher impede mappings duplicados ou conflitantes entre ações.

### Analógico e zona morta

- **Usar analógico esquerdo para navegar:** ativa ou desativa a navegação pelo analógico.
- **Zona morta do analógico:** valor entre 1000 e 32000.
  - Valores menores deixam o analógico mais sensível.
  - Valores maiores evitam movimentos acidentais causados por drift.

## Capas

O launcher tenta baixar as capas automaticamente pela internet. Se a capa de um jogo não for encontrada, o card exibe o cartucho padrão **SEM CAPA**.

Você também pode adicionar capas manualmente:

- Coloque um arquivo `NomeDaRom.png` ou `NomeDaRom.jpg` na pasta de capas.
- O nome deve ser igual ao nome do arquivo da ROM, sem a extensão.
- Exemplo: `Super Mario Bros.nes` → `Super Mario Bros.png`.

Para corrigir uma capa errada, substitua o arquivo de imagem na pasta de capas pelo arquivo correto.

## Onde ficam os dados

- **Configurações:** `%AppData%\NestopiaLauncher\configuracao.json`
- **Favoritos e recentes:** `%AppData%\NestopiaLauncher\biblioteca.json`

Para restaurar o launcher ao estado inicial, feche o programa e apague a pasta `%AppData%\NestopiaLauncher`.

Atualizar o launcher não apaga as configurações, favoritos ou recentes. O executável é portátil, mas os dados ficam no perfil do usuário do Windows.

## Solução de problemas

### O Windows mostra um aviso ao abrir

O executável não possui assinatura digital. Se aparecer o SmartScreen, clique em **Mais informações → Executar assim mesmo**. Se o antivírus bloquear, adicione o launcher à lista de exceções.

### Nenhuma ROM aparece

- Confira se a pasta de ROMs está correta nas configurações.
- Verifique se as extensões dos arquivos estão na lista **Extensões aceitas**.
- Confirme se as ROMs são arquivos válidos e não estão compactadas em um formato não suportado.

### O jogo não abre

- Confira se o caminho do `nestopia.exe` está correto.
- Verifique se o arquivo da ROM existe e pode ser aberto.
- Se o emulador abrir, mas o jogo não carregar, teste a ROM diretamente no Nestopia JG.

### As capas não são baixadas

- Verifique sua conexão com a internet e o firewall.
- Confirme se a pasta de capas tem permissão de escrita.
- Adicione a capa manualmente na pasta de capas com o nome correto.

### O controle não responde

- Conecte o controle antes de abrir o launcher.
- Confira se ele aparece nos dispositivos de jogo do Windows.
- Para controles XInput, verifique se o driver está instalado corretamente.
- Para adaptadores de PS2/DualShock, confira se o adaptador é reconhecido como gamepad. Se necessário, troque de porta USB ou reinstale o driver do adaptador.
- Abra **Configurações → Controle** e remapeie os botões.

### O analógico se move sozinho

Aumente a **zona morta do analógico** nas configurações. Valores maiores ignoram pequenos movimentos involuntários.

### As configurações foram perdidas

- Verifique se a pasta `%AppData%\NestopiaLauncher` existe e tem permissão de escrita.
- Evite executar o launcher com usuários diferentes do Windows.
- Se você apagou a pasta, as configurações voltam ao padrão.

### O jogo não fecha com Start + Back

- Confirme se o combo está mapeado em **Configurações → Controle**.
- O launcher encerra apenas o processo do jogo que ele mesmo iniciou.
- Se o jogo já foi fechado manualmente, o atalho não terá efeito.

### O adaptador de PS2/DualShock não é reconhecido

- Teste o adaptador em outro jogo ou no painel de dispositivos do Windows.
- Troque de porta USB.
- Reinstale o driver do adaptador.
- Se o adaptador não aparecer como gamepad, o launcher não conseguirá lê-lo.

## Perguntas frequentes

### Preciso instalar o .NET?

Não. O executável é self-contained e já inclui tudo o que precisa para rodar.

### O launcher inclui ROMs?

Não. As ROMs não são distribuídas com o launcher. Use apenas jogos que você tem direito de usar.

### O launcher inclui o Nestopia JG?

Sim. O pacote do release inclui o emulador. Na primeira configuração, aponte para o `nestopia.exe` que veio junto no pacote.

### Funciona com outros emuladores?

O launcher foi feito para o Nestopia JG. Outros emuladores podem funcionar se aceitarem o caminho da ROM como argumento, mas não há garantia de compatibilidade.

### Funciona com controle de PS2/DualShock?

Sim, via DirectInput. Como a numeração dos botões varia conforme o adaptador, remapeie as ações na primeira vez.

### Funciona no Linux ou macOS?

Não. O launcher é feito para Windows 10/11 (64 bits).

### Como atualizar?

Baixe o novo pacote na página de Releases e substitua os arquivos do launcher. Suas configurações, favoritos e recentes permanecem salvos em `%AppData%\NestopiaLauncher`.

### Como desinstalar?

Apague a pasta do launcher. Se quiser remover também as configurações e favoritos, apague a pasta `%AppData%\NestopiaLauncher`.

### Posso usar teclado e controle ao mesmo tempo?

Sim. O launcher aceita entrada de teclado e controle simultaneamente.

### O que é a zona morta do analógico?

É a quantidade mínima de movimento necessária para o analógico ser considerado pressionado. Aumentar esse valor evita que pequenos movimentos ou drift sejam interpretados como navegação.

## Licença

O launcher **Nestopia Launcher** é distribuído sob a licença **MIT**. Consulte o arquivo [LICENSE](https://github.com/keuyn/NestopiaLauncher/blob/main/LICENSE) para mais detalhes.

O emulador **Nestopia JG** é um projeto separado, distribuído sob sua própria licença (GPL). Os arquivos de licença do emulador estão incluídos no pacote do release.

### Aviso legal

- Este projeto não é afiliado à Nintendo.
- NES é uma marca registrada da Nintendo.
- Nenhuma ROM é distribuída com o launcher.
- Baixe e use apenas jogos que você tem direito de usar.

## Créditos

- **Autor:** Keuyn
  - GitHub: [github.com/keuyn](https://github.com/keuyn)
  - Instagram: [@keurynn_](https://instagram.com/keurynn_)
- **Nestopia JG:** Jolly Good Emulation Team
- **Capas:** Libretro Thumbnails
- **Ícone:** Keuyn

Obrigado a todos que testaram e ajudaram a melhorar o launcher.

## Links úteis

- [Releases](https://github.com/keuyn/NestopiaLauncher/releases/latest)
- [Issues](https://github.com/keuyn/NestopiaLauncher/issues)
- [Licença MIT](https://github.com/keuyn/NestopiaLauncher/blob/main/LICENSE)
- [GitHub do autor](https://github.com/keuyn)
- [Instagram do autor](https://instagram.com/keurynn_)
- [Download de ROMs de NES](https://www.romsgames.net/roms/nintendo)

## Versão

2.0.0
