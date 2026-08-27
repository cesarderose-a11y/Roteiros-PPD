---
title: "Como executar os roteiros de OpenMP"
publishedAt: "2026-08-27"
summary: "Instruções para configurar os ambientes de execução dos roteiros OpenMP"
---

## Execução dos roteiros em máquina local

### Opção 1: terminal de um máquina rodando Linux nativo

Esta é a opção mais simples pois necessita apenas a instalação do compilador gcc que já tem suporte nativo ao OpenMp a partir da versão 4.2.0 de 2007 (ver instruções específicas de instalação do gcc na sua distribuição).  

> atentar que versões mais recentes do gcc tem suporte para versões mais novas do OpenMP

### Opção 2: terminal de uma máquina rodando MacOS 

Esta é a opção também requer pouca instalação adicional pois o terminal nativo do MacOS executa uma versão de Unix (baseado no FreeBSD e Darwin). Isso significa que você encontrará praticamente a mesma interface de linha de comando do Linux, com algumas pequenas variações de comportamento e ferramentas de sistema distintas. Como precisamos apenas do gcc a partir da versão 4.2.0 de 2007 instalado, estas pequenas variações não atrapalham a execução dos roteiros (ver instruções específicas de instalação do gcc no MacOS). 

> atentar que o MacOs vem com uma versão nativa de compilador para C chamada clang (com um alias para gcc), que tem também suporte ao OpenMP, mas com algumas pequenas particularidades que podem atrapalhar as execuções dos nosso roteiros. Para fins de compatibilidade o mais tranquilo é instalar o gcc e garantir que está chamado a versão correta.

Para verificar a versão do gcc instalada na máquina utilizar comando:

```sh
gcc --version
```

ou 

```sh
gcc-14 --version
```
> substituir o número `14` pela versão do gcc instalado na sua máquina

### Opção 3: emulador de Linux em uma máquina rodando Windows 

Esta é a opção requer a instalação adicional de um emulador de Linux no Windows chamado WSL (Windows Subsystem for Linux), mas que é bastante simples nas versões 10 e 11 do Windows. Abrir um terminal no PowerSehell como administrador e executar o comando:

```sh
wsl --install
```

Esse comando habilita os recursos necessários do sistema, baixa o kernel do Linux mais recente e instala a distribuição padrão (Ubuntu). Após reiniciar a máquina, a janela do Ubuntu será aberta automaticamente. Aguarde a inicialização e digite um nome de usuário e senha para o ambiente Linux. Depois reinicie o computador e execute o WSL. No terminal faça a instalação do pacote `build-essential` que inclui o gcc com os comandos:

```sh
sudo apt update && sudo apt upgrade -y
sudo apt install build-essential -y
```
Agora verifique a versão instalada do gcc com o comando:

```sh
gcc --version
```
## Execução dos roteiros em máquina remota (LAD)

