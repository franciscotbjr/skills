---
status: triaged
title: Aplicar as personas especialistas no repositório
origin: idea
destination: O-002 (backlog.md)
---

# Problema

A iteração [004-personas-especialistas](../../history/004-personas-especialistas.md)
produziu a pesquisa pura das duas personas no vault Jandi
(`Agente - Personas Especialistas em Autoria de Agent Skills e em Vieses Linguísticos de LLMs.md`),
mas o repositório ainda usa a Persona antiga do `AGENTS.md`, escrita antes da
pesquisa e sem ancoragem nela.

## Ação

Consolidar a pesquisa no repo, nos moldes do que o stateful-spec fez com a
persona SDD (`AGENTS.md` + `.stateful-spec/persona.md` + `persona-reference.md`):

- Derivar do doc do vault um `persona.md` operacional (as duas personas:
  A = base de autoria de skills; B = extensão de vieses linguísticos).
- Fazer o binding no `AGENTS.md`, confrontando a Persona atual com a pesquisa
  (o confronto ficou explicitamente adiado para esta iteração — ver Decisões
  da 004).

## O que não faremos agora

- Não alterar as skills existentes; o escopo é a persona e seu binding.
