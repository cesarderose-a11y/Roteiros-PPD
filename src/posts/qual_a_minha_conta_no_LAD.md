---
title: "Qual é a conta do meu grupo no LAD e como troco a senha"
publishedAt: "2026-11-9"
summary: "Instruções para acessar o LAD com a conta do grupo e trocar a senha padrão."
---

## Compilação em máquina local

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

## Padrão de contas do LAD (um por grupo)

Bem vindo ao Laboratório de Alto Desempenho - LAD IDEIA/PUCRS.

Para que os alunos utilizem os nossos serviços, contas foram criadas para você. Os detalhes são os seguintes:

Servidor: atlantica.lad.pucrs.br
 
Acesso de casa (ou rede Wifi da PUCRS) pela sparta (com credenciais de aluno): ssh user@sparta.pucrs.br (usar primeira parte do e-mail PUCRS como usuário e senha do e-mail)
 
Acesso da PUCRS ou da sparta (com credenciais do grupo, TTT é a turma (310 ou 320) e GG é o número do grupo - ver abaixo): 

ssh cpTTTGG@atlantica.lad.pucrs.br

Usernames: cpTTT00, cpTTT01 , cpTTT02, ... cpTTT25

Usuários (por ordem do número do grupo):  00 Professor, 01 Grupo 01, 02 Grupo 02, 03 Grupo 03, e assim por diante ...
 
Senha inicial (todos os usuários): CUtSpNiBoCMUQMGLwKW6

Por favor, troquem a senha assim que for possível.

## Procedimento para mudança de senha

1. Logar na hospedeira do cluster atlantica

ssh cpTTTGG@atlantica.lad.pucrs.br

3. Trocar a senha:
   
$ yppasswd

e seguir as instruções apresentadas.
