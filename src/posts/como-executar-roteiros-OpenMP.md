---
title: "Como executar os roteiros de OpenMP"
publishedAt: "2026-08-27"
summary: "Instruções para configurar os ambientes de execução dos roteiros OpenMP"
---

## Execução dos roteiros em máquina local

### Opção 1: terminal de um máquina rodando Linux nativo

Esta é a opção mais simples pois necessita apenas a instalação do compilador gcc que já tem suporte nativo ao OpenMp a partir da versão 4.2.0 de 2007 (ver instruções específicas de instalação sua distribuição).  

> atentar que versões mais recentes do gcc tem suporte para versões mais novas do OpenMP

### Opção 2: terminal de uma máquina rodando MacOS 

Esta é a opção também requer pouca instalação adicional pois o terminal nativo do MacOS executa uma versão de Unix (baseado no FreeBSD e Darwin). Isso significa que você encontrará praticamente a mesma interface de linha de comando do Linux, com algumas pequenas variações de comportamento e ferramentas de sistema distintas. Como precisamos apenas do gcc a partir da versão 4.2.0 de 2007 instalado, estas pequenas variações não atrapalham a execução dos roteiros (ver instruções específicas de instalação do gcc no MacOS). 

> atentar que o MacOs vem com uma versão nativa de compilador para C chamada clang (com um alias para gcc), que tem também suporte ao OpenMP, mas com algumas pequenas particularidades que podem atrapalhar as execuções dos nosso roteiros. Para fins de compatibilidade o mais tranquilo é instalar o gcc e garantir que está chamado a versão correto.



### Opção 3: emulador de Linux em uma máquina rodando Windows 

## Execução dos roteiros em máquina remota (LAD)




```sh
mpicc file.c -o file_exec
```

## Execução em máquina local

```sh
mpirun -np 1 ./file_exec
```

> onde `np` é o número de processos MPI que serão criados.

## Compilação em máquina remota (LAD)

```sh
mpicc file.c -o file_exec
```

## Execução em máquina remota (LAD)

```sh
srun -N 2 -n 2 ./file_exec
```

> onde `N` é o número de nodos alocados na máquina e `n` o número total de processos MPI que serão criados.

> atente que a saída de tela só aparece no terminal **após** a execução toda do programa (`MPI_FINALIZE`).

## Execução exclusiva na máquina (para fins de medição de tempo)

Para realizar uma execução com o propósito de medir o tempo transcorrido é importante garantir que será realizada sem a interferência de outra aplicação na mesma máquina, ou seja, com a utilização esclusiva dos recursos. Pra isto usaremos o parâmetro **--exclusive**.

```sh
srun --exclusive -N 2 -n 2 ./file_exec
```

## Execução de mais processos que processadores (acima do HT)

```sh
srun --oversubscribe -N 2 -n 2 ./file_exec
```

