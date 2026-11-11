# Nestopia Launcher

[![Release](https://img.shields.io/github/v/release/keuyn/NestopiaLauncher?style=flat-square)](https://github.com/keuyn/NestopiaLauncher/releases/latest)
[![Licença: MIT](https://img.shields.io/badge/licen%C3%A7a-MIT-green?style=flat-square)](https://github.com/keuyn/NestopiaLauncher/blob/main/LICENSE)
[![Plataforma](https://img.shields.io/badge/plataforma-Linux%20%7C%20Windows%2010%2F11-blue?style=flat-square)]()

Launcher visual para o emulador **Nestopia JG**, com grade de capas, busca em tempo real, favoritos, jogos recentes, filtros, fundo dinâmico, efeitos sonoros e suporte a controles — para **Linux** e **Windows**.

> **Download rápido:** baixe a versão mais recente na página de [Releases](https://github.com/keuyn/NestopiaLauncher/releases/latest).

## Índice

- [Sobre o projeto](#sobre-o-projeto)
- [Recursos](#recursos)
- [Requisitos](#requisitos)
- [Download e instalação](#download-e-instalação)
- [Instalando o Nestopia no Linux](#instalando-o-nestopia-no-linux)
- [Primeira configuração](#primeira-configuração)
- [Configurando o controle no Nestopia](#configurando-o-controle-no-nestopia)
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

A partir da versão 2.1.0 o launcher é multiplataforma: no **Linux** ele roda como AppImage (com a libSDL2 embutida) ou como binário único; no **Windows** segue igual às versões anteriores. As ROMs **não** são incluídas.

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
- Suporte a controles via SDL2: Xbox (XInput), DualShock/DualSense, Switch Pro e genéricos USB
- Controles sem mapeamento SDL aparecem como **D1**–**D32** (como o DirectInput da versão Windows)
- Download automático de capas pela internet (Libretro Thumbnails)
- Analógico esquerdo para navegar, com zona morta configurável
- Janela Sobre com versão, links do autor e link para download de ROMs

## Requisitos

- **Linux** x64 (qualquer distro com glibc ≥ 2.35) ou **Windows 10/11** x64
- Não é necessário instalar o .NET
- No Linux, o AppImage já inclui a libSDL2 (controles e som); sem libSDL2 o launcher funciona com teclado e mouse
- ROMs de NES não são incluídas
- Um controle é opcional; teclado e mouse funcionam normalmente

## Download e instalação

### Linux (AppImage)

1. Acesse a página de [Releases](https://github.com/keuyn/NestopiaLauncher/releases/latest).
2. Baixe o arquivo `NestopiaLauncher-<versão>-x86_64.AppImage`.
3. Dê permissão de execução e execute:

```bash
chmod +x NestopiaLauncher-*.AppImage
./NestopiaLauncher-*.AppImage
```

Para integrar ao menu do sistema, use o [AppImageLauncher](https://github.com/TheAssassin/AppImageLauncher) ou copie o arquivo para `~/.local/bin`.

> Se o AppImage não executar, sua distro pode estar sem a libfuse2. Instale o pacote `libfuse2` ou rode com `APPIMAGE_EXTRACT_AND_RUN=1 ./NestopiaLauncher-*.AppImage`.

### Linux (tarball)

Baixe o `NestopiaLauncher-<versão>-linux-x64.tar.gz`, extraia e execute:

```bash
tar xzf NestopiaLauncher-*-linux-x64.tar.gz
./NestopiaLauncher
```

O tarball traz o binário único e a `libSDL2-2.0.so.0` lado a lado — mantenha os dois arquivos na mesma pasta.

### Windows

Baixe o pacote `.zip` da Release, extraia e execute `NestopiaLauncher.exe`. Se o Windows exibir o aviso do SmartScreen, clique em **Mais informações** e depois em **Executar assim mesmo**.

O launcher é portátil: não precisa de instalador. As configurações e os favoritos ficam salvos na pasta do usuário, então atualizar ou mover o executável não apaga seus dados.

## Instalando o Nestopia no Linux

O launcher é só a interface: quem emula o jogo é o **Nestopia**. No Linux ele não vem no AppImage/tarball, então instale uma vez antes de configurar o launcher.

Há dois caminhos:

1. **Nestopia nativo** (recomendado) — instalado pelo gerenciador de pacotes da sua distro.
2. **Nestopia do Windows via wine** — usando o `nestopia.exe` do pacote `.zip` do release.

### Debian, Ubuntu, Mint, Pop!_OS, Zorin e derivados

O pacote `nestopia` está nos repositórios oficiais (no Ubuntu, na seção *universe*):

```bash
sudo apt update
sudo apt install nestopia
```

O executável fica em `/usr/games/nestopia`.

### openSUSE (Tumbleweed e Leap)

```bash
sudo zypper install nestopia
```

### Arch Linux, Manjaro e EndeavourOS

O repositório oficial só tem o núcleo para RetroArch (`libretro-nestopia`), não o programa standalone. O Nestopia está no **AUR**:

```bash
yay -S nestopia
# ou
paru -S nestopia
```

### Fedora

Não existe pacote standalone nos repositórios oficiais (só o núcleo `libretro-nestopia`). Use uma das alternativas:

- compilar do código-fonte: [0ldsk00l/nestopia](https://github.com/0ldsk00l/nestopia)
- usar o `nestopia.exe` do Windows via wine (veja abaixo)

### Outras distros

- Se a distro tiver o Nestopia nos repositórios, instale pelo gerenciador de pacotes (`nestopia`).
- Caso contrário, compile do código-fonte: [0ldsk00l/nestopia](https://github.com/0ldsk00l/nestopia).
- Ou use o `nestopia.exe` do Windows via wine.

> Evite usar o `.deb` oficial do Nestopia 2.0.0 (do projeto Jolly Good) em distros antigas: ele foi compilado para **glibc 2.43** e exige **SDL3** e **Qt 6.10+**, então só roda nas distros mais recentes. O pacote da própria distro é a opção mais compatível.

### Testando o emulador

Abra uma ROM direto pelo terminal para confirmar que o Nestopia funciona:

```bash
nestopia /caminho/para/jogo.nes
```

Se abrir o jogo, o emulador está pronto. Depois, no launcher, informe esse comando (ou o caminho completo, como `/usr/games/nestopia`) no campo **Nestopia (executável)**.

### Opção: usar o Nestopia do Windows via wine

Se preferir o mesmo `nestopia.exe` que vem no pacote `.zip` do release, instale o wine:

| Distro | Comando |
| --- | --- |
| Debian/Ubuntu/Mint/Pop!_OS | `sudo apt install wine` |
| Fedora | `sudo dnf install wine` |
| Arch/Manjaro | `sudo pacman -S wine` |
| openSUSE | `sudo zypper install wine` |

Depois, no launcher, aponte o campo **Nestopia (executável)** para o `nestopia.exe`. Quando o caminho termina em `.exe`, o launcher executa automaticamente via `wine`, passando a ROM como argumento.

## Primeira configuração

> **Ordem recomendada:** instale o emulador, **configure o controle dentro do Nestopia** (seção [Configurando o controle no Nestopia](#configurando-o-controle-no-nestopia)) e só então abra o launcher. São duas configurações independentes.

Na primeira execução, pressione **F2** ou o botão **Select/Back** do controle para abrir a janela **Configurações**.

Preencha os campos:

- **Nestopia (executável):** informe o executável do emulador. No Windows, selecione o `nestopia.exe` que veio junto no pacote ou a sua instalação existente. No Linux, use um emulador nativo (ex.: `nestopia` ou o caminho completo `/usr/games/nestopia`) ou o `nestopia.exe` do Windows — nesse caso o launcher o executa via [wine](https://www.winehq.org/), se estiver instalado. Também vale um nome de comando presente no `PATH`.
- **Pasta de ROMs:** selecione a pasta onde estão ou serão colocadas as ROMs. Crie uma pasta se ainda não tiver.
- **Pasta de capas:** selecione uma pasta para as capas. Pode ser uma pasta vazia; o launcher baixa e organiza os arquivos.
- **Extensões aceitas:** por padrão `.nes, .zip, .fds`. Adicione outras extensões se precisar, separadas por vírgula.
- **Máx. recentes:** quantidade de jogos exibidos no filtro Recentes (1 a 100).
- **Efeitos sonoros:** ativa ou desativa os sons de navegação e seleção.
- **Fundo dinâmico:** ativa ou desativa o fundo desfocado com a capa do jogo selecionado.

Clique em **Salvar**. Depois, coloque suas ROMs na pasta configurada e volte para a tela principal.

> Se a pasta de capas estiver vazia, o launcher tenta baixar as capas automaticamente. Jogos sem capa usam o cartucho padrão **SEM CAPA**.

## Configurando o controle no Nestopia

**Configurar o controle no Nestopia Launcher é diferente de configurar no Nestopia.** São duas camadas separadas:

| Onde | O que configura |
| --- | --- |
| **Nestopia** (emulador) | Os botões **dentro do jogo**: direcional, A, B, Start, Select e turbo do Player 1 (e Player 2) |
| **Nestopia Launcher** | As ações **do launcher**: Jogar, Favoritar, Filtro, Configurações e Encerrar jogo |

O launcher **não** repassa nem simula botões para o jogo. Ele apenas abre o emulador com a ROM. Por isso, o controle precisa ser configurado primeiro **dentro do Nestopia** — do contrário o jogo abre e os botões não fazem nada (ou ficam trocados).

### Passo a passo no Nestopia

1. Conecte o controle **antes** de abrir o emulador.
2. Abra o Nestopia **diretamente** (fora do launcher) e carregue uma ROM em **File → Open**.
3. Abra **Options → Input** (em versões mais novas o item pode aparecer como *Input* / *Entrada* nas opções).
4. Selecione o **Pad 1** (Player 1).
5. Clique em **Set All** (ou clique item por item) e pressione o botão correspondente no controle, nesta ordem: **cima, baixo, esquerda, direita, B, A, Select, Start** (e os botões de turbo, se quiser).
6. Clique em **OK**. O próprio Nestopia salva a configuração.
7. Feche o Nestopia e abra o launcher normalmente.

No Linux, as configurações do emulador ficam na pasta dele (por exemplo `~/.config/nestopia/`), não no launcher.

Se estiver usando o `nestopia.exe` via **wine**, o menu é o mesmo: o wine entrega o controle ao programa do Windows, e a configuração é feita dentro da janela do Nestopia.

### Depois, no launcher

Com o jogo já respondendo ao controle, configure o launcher em **Configurações → Controle** (veja [Controles](#controles)). Aqui você define apenas quais botões navegam na grade, abrem o jogo, favoritam, alternam filtro, abrem as configurações e encerram o jogo.

> Regra prática: se o botão funciona no launcher mas não no jogo, o ajuste é no **Nestopia**. Se funciona no jogo mas não no launcher, o ajuste é no **launcher**.

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

### Controle (padrões)

| Botão | Ação |
| --- | --- |
| D-Pad | Navegar pela grade |
| Analógico esquerdo | Navegar pela grade |
| A | Abrir o jogo selecionado |
| X | Favoritar ou desfavoritar |
| Y | Alternar filtro |
| Back / Select | Abrir as configurações |
| Start + Back | Encerrar o jogo em execução |

> Enquanto um jogo está aberto, o launcher fica em segundo plano e **só responde ao atalho de encerrar** — os demais botões pertencem ao jogo. Ao fechar o jogo, o launcher volta com o foco do teclado pronto para uso.
>
> Os botões acima são os padrões para controles no layout Xbox/PlayStation (Xbox 360/One/Series, DualShock 4, DualSense etc., lidos via SDL2). Todos podem ser remapeados em **Configurações → Controle**.

### Controles genéricos (adaptadores USB)

Controles e adaptadores sem mapeamento no banco da SDL — comum em adaptadores de PS1/PS2 para USB — são lidos como joystick genérico e aparecem na captura como **D1**, **D2**, etc. A numeração varia conforme o adaptador.

Na primeira vez que usar um controle genérico, remapeie as ações:

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
- Adaptadores duplos com uma porta vazia não geram navegação fantasma: a posição de repouso de cada controle é aprendida quando ele é aberto.

## Capas

O launcher tenta baixar as capas automaticamente pela internet (Libretro Thumbnails). Se a capa de um jogo não for encontrada, o card exibe o cartucho padrão **SEM CAPA**.

Você também pode adicionar capas manualmente:

- Coloque um arquivo `NomeDaRom.png` ou `NomeDaRom.jpg` na pasta de capas.
- O nome deve ser igual ao nome do arquivo da ROM, sem a extensão.
- Exemplo: `Super Mario Bros.nes` → `Super Mario Bros.png`.

Para corrigir uma capa errada, substitua o arquivo de imagem na pasta de capas pelo arquivo correto.

## Onde ficam os dados

- **Linux:** `~/.config/NestopiaLauncher/`
  - `configuracao.json` — configurações
  - `biblioteca.json` — favoritos e recentes
- **Windows:** `%AppData%\NestopiaLauncher\` (mesmos arquivos)

Para restaurar o launcher ao estado inicial, feche o programa e apague a pasta acima.

Atualizar o launcher não apaga as configurações, favoritos ou recentes. O executável é portátil, mas os dados ficam no perfil do usuário.

## Solução de problemas

### O AppImage não executa (Linux)

Distro sem `libfuse2` (comum nas mais novas). Duas opções:

```bash
sudo apt install libfuse2        # ou o equivalente da sua distro
APPIMAGE_EXTRACT_AND_RUN=1 ./NestopiaLauncher-*.AppImage   # alternativa sem instalar nada
```

### O Windows mostra um aviso ao abrir

O executável não possui assinatura digital. Se aparecer o SmartScreen, clique em **Mais informações → Executar assim mesmo**. Se o antivírus bloquear, adicione o launcher à lista de exceções.

### Nenhuma ROM aparece

- Confira se a pasta de ROMs está correta nas configurações.
- Verifique se as extensões dos arquivos estão na lista **Extensões aceitas**.
- Confirme se as ROMs são arquivos válidos e não estão compactadas em um formato não suportado.

### O jogo não abre

- Confira o caminho do executável do Nestopia.
- No Linux, um `nestopia.exe` do Windows exige o [wine](https://www.winehq.org/) instalado; executáveis nativos precisam de permissão de execução (`chmod +x`).
- Se o emulador abrir, mas o jogo não carregar, teste a ROM diretamente no Nestopia JG.

### As capas não são baixadas

- Verifique sua conexão com a internet e o firewall.
- Confirme se a pasta de capas tem permissão de escrita.
- Adicione a capa manualmente na pasta de capas com o nome correto.

### O controle não responde

- Conecte o controle antes de abrir o launcher (ele também detecta controles conectados depois).
- No Linux, veja se o controle aparece em `/dev/input/js*` ou em `cat /proc/bus/input/devices`. Se aparecer só para o root, o problema é permissão: rode o launcher a partir da sessão de desktop normal (não via `sudo`/SSH).
- Controles sem mapeamento SDL (adaptadores genéricos) têm os botões capturados como **D1**–**D32**: remapeie as ações em **Configurações → Controle**.
- Sem a libSDL2 o launcher não lê controle — no Linux o AppImage já traz a biblioteca embutida; no Windows coloque `SDL2.dll` junto do executável.
- O controle funciona mesmo com a janela sem foco.

### O controle funciona no launcher, mas não no jogo

Isso é normal na primeira vez: são duas configurações diferentes.

- Configure o controle **dentro do Nestopia**, em **Options → Input** → **Pad 1** → **Set All** (veja [Configurando o controle no Nestopia](#configurando-o-controle-no-nestopia)).
- Confirme que abriu uma ROM e que o emulador está com foco (clique na janela do jogo).
- Se estiver usando o `nestopia.exe` via wine, o controle é entregue pelo wine; configure dentro da janela do Nestopia.
- Botões trocados (A/B invertidos, direcional rotacionado) também são ajustados no **Nestopia**, não no launcher.

### O analógico se move sozinho

Aumente a **zona morta do analógico** nas configurações. Valores maiores ignoram pequenos movimentos involuntários.

### As configurações foram perdidas

- Verifique se a pasta `~/.config/NestopiaLauncher` (Linux) ou `%AppData%\NestopiaLauncher` (Windows) existe e tem permissão de escrita.
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
- No Linux, o adaptador deve aparecer em `/dev/input/js*` (ou como evento em `/dev/input/event*`) com permissão do seu usuário; adaptadores duplos podem expor duas portas — a porta vazia não atrapalha a navegação.

## Perguntas frequentes

### Preciso instalar o .NET?

Não. O executável é self-contained e já inclui tudo o que precisa para rodar.

### Preciso instalar a SDL2?

No Linux, não: o AppImage e o tarball já trazem a `libSDL2` embutida. No Windows, a biblioteca é opcional — sem `SDL2.dll` o launcher funciona com teclado e mouse, sem som e sem controle.

### O launcher inclui ROMs?

Não. As ROMs não são distribuídas com o launcher. Use apenas jogos que você tem direito de usar.

### O launcher inclui o Nestopia JG?

No **Windows**, sim: o pacote do release inclui o emulador, e na primeira configuração você aponta para o `nestopia.exe` que veio junto.

No **Linux**, não: o AppImage e o tarball trazem só o launcher. Instale o Nestopia à parte — veja [Instalando o Nestopia no Linux](#instalando-o-nestopia-no-linux).

### Preciso configurar o controle no Nestopia também?

Sim. O launcher mapeia apenas as ações dele (Jogar, Favoritar, Filtro, Configurações, Encerrar jogo). Os botões **do jogo** são configurados dentro do Nestopia, em **Options → Input**. Veja [Configurando o controle no Nestopia](#configurando-o-controle-no-nestopia).

### Funciona com o nestopia.exe do Windows no Linux?

Sim. Se o caminho configurado apontar para um `.exe`, o launcher o executa via [wine](https://www.winehq.org/) automaticamente (precisa do wine instalado). Também dá para usar um emulador nativo do Linux ou um nome de comando do `PATH`.

### Funciona com outros emuladores?

O launcher foi feito para o Nestopia JG. Outros emuladores podem funcionar se aceitarem o caminho da ROM como argumento, mas não há garantia de compatibilidade.

### Funciona com controle de PS2/DualShock?

Sim. Controles com mapeamento SDL conhecido (DualShock 3/4, DualSense) funcionam com o layout A/B/X/Y direto. Adaptadores genéricos de PS1/PS2 para USB aparecem como **D1**–**D32**: remapeie as ações na primeira vez.

### Funciona no Linux?

Sim — desde a versão 2.1.0, via AppImage ou binário único. As versões anteriores eram só para Windows.

### Como atualizar?

Baixe o novo pacote na página de Releases e substitua o arquivo do launcher. Suas configurações, favoritos e recentes permanecem salvos (Linux: `~/.config/NestopiaLauncher`; Windows: `%AppData%\NestopiaLauncher`).

### Como desinstalar?

Apague o AppImage (ou a pasta do launcher). Se quiser remover também as configurações e favoritos, apague a pasta de dados indicada acima.

### Posso usar teclado e controle ao mesmo tempo?

Sim. O launcher aceita entrada de teclado e controle simultaneamente.

### O que é a zona morta do analógico?

É a quantidade mínima de movimento necessária para o analógico ser considerado pressionado. Aumentar esse valor evita que pequenos movimentos ou drift sejam interpretados como navegação.

## Licença

O launcher **Nestopia Launcher** é distribuído sob a licença **MIT**. Consulte o arquivo [LICENSE](https://github.com/keuyn/NestopiaLauncher/blob/main/LICENSE) para mais detalhes.

O emulador **Nestopia JG** é um projeto separado, distribuído sob sua própria licença (GPL).

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
- [Nestopia UE (código-fonte)](https://github.com/0ldsk00l/nestopia)
- [Nestopia JG (Jolly Good)](https://gitlab.com/jgemu/nestopia)
- [Wine](https://www.winehq.org/)

## Versão

2.1.0
