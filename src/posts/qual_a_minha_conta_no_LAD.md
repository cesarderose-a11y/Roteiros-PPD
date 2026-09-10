---
title: "Qual é a conta do meu grupo no LAD e como troco a senha"
publishedAt: "2026-11-9"
summary: "Instruções para acessar o LAD com a conta do grupo e trocar a senha padrão."
---

## Padrão de contas do LAD (um por grupo)

Bem vindo ao Laboratório de Alto Desempenho - LAD IDEIA/PUCRS.

Para que os alunos utilizem os nossos serviços, contas foram criadas para você. Os detalhes são os seguintes:

Servidor: atlantica.lad.pucrs.br
 
Acesso de casa (ou rede Wifi da PUCRS) pela sparta (com credenciais de aluno): 

```sh
ssh usuário@sparta.pucrs.br 
```

> usar primeira parte do e-mail PUCRS como usuário (ex: cesar.derose) e a senha do e-mail 

Acesso da PUCRS ou da sparta: 

```sh
ssh cpTTTGG@atlantica.lad.pucrs.br
```

> onde `TTT` é o número da turma (310 ou 320) e `GG` o número do grupo (01, 02 etc.)
> `00` é a conta do professor
 
Senha inicial (turma 310): CUtSpNiBoCMUQMGLwKW6
Senha inicial (turma 320): Ijmupb2w6gE3qLBtbhpH

Por favor, troquem a senha assim que for possível.

## Procedimento para mudança de senha

1. Logar na hospedeira do cluster atlantica

```sh
ssh cpTTTGG@atlantica.lad.pucrs.br
```
> onde `TTT` é o número da turma (310 ou 320) e `GG` o número do grupo (01, 02 etc.)

2. Trocar a senha:

```sh
yppasswd
```

e seguir as instruções apresentadas.
