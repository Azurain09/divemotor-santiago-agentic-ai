# Divemotor Santiago - Agentic AI Evaluation

An applied Agentic AI domain for vehicle sales operations, developed in the `tau2-bench` evaluation environment. The project models how an agent can assist with vehicle discovery, quotations, purchase workflows, approval checks, and policy-aware decisions through controlled tools.

## What I built

- A domain model for vehicle-sales workflows.
- Six controlled business tools for agent actions.
- Automated tests for the domain tools.
- Business policies and a RAG-oriented policy version.
- A simulated evaluation setup with 20 business and adversarial tasks.
- Prompt-engineering experiments and repeated simulation analysis.

## Evaluation work

The work focused on measurement rather than a single successful conversation.

| Stage | Evaluation approach | Result |
| --- | --- | --- |
| Initial evaluation | 20 tasks x 10 runs | 150/200 successful simulations |
| Hard-task baseline | 10 tasks x `pass^5` | 30/50 successful simulations |
| RAG experiment A | Full policy, no RAG | 30/50 successful simulations |
| RAG experiment B | Header-based retrieval | 31/50 successful simulations |
| RAG experiment C | Fixed-size retrieval chunks | 30/50 successful simulations |
| RAG experiment D | Retrieval plus planning tool | 24/50 successful simulations |

The main finding was that retrieval can help an agent recover specific policy rules, but it does not automatically solve failures around conversational closure, identity checks, or adversarial prompts. Adding reasoning steps also increased `max_steps` failures in this evaluation.

## Technical concepts

- Agentic AI with controlled tools
- Policy-constrained actions
- Simulated users and task-based evaluation
- Prompt engineering as an experiment
- RAG, embeddings, and policy retrieval
- Regression analysis across repeated simulations

## Project structure

`src/tau2/domains/divemotor_santiago/` contains the domain model, environment, and tools.

`tests/domain_tests/divemotor_santiago/` contains automated tool tests.

`data/` contains public policy documents only.

## Privacy and safety

- This public version excludes the simulated database, raw task inputs, raw simulation logs, credentials, caches, and local configuration.
- The original evaluation used synthetic scenarios. No customer or operational production data is included here.
- This repository is a portfolio case study, not a production vehicle-sales system.

## Attribution

This domain was developed as coursework on top of the open-source [`tau2-bench`](https://github.com/sierra-research/tau2-bench) framework by Sierra Research, released under the MIT License. This repository contains my domain-specific implementation and public documentation, not a copy of the full framework.
