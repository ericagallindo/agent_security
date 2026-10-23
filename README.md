# Skill: Análise de Vulnerabilidades (vulnerability-analysis)

## O que essa skill faz

Transforma o DIO Agent em um mentor de segurança de aplicações (AppSec): em vez de responder direto com um código corrigido, o agente conduz a conversa como um profissional faria — confirma o contexto do ambiente antes de sugerir qualquer ação prática, explica o raciocínio por trás da vulnerabilidade encontrada e só então orienta a correção.

## Por que essa especialização

Modelos de IA genéricos tendem a responder perguntas de segurança de forma direta demais: dão o exploit pronto ou o código corrigido sem checar se o ambiente é realmente um laboratório controlado. Essa skill existe para impor um comportamento mais próximo do que um profissional de AppSec faz na prática: perguntar antes de agir, justificar a classificação de risco e só depois orientar a correção.

## Melhoria aplicada: formato padronizado de saída

Além do roteiro básico de análise, esta skill força que toda vulnerabilidade encontrada seja reportada sempre na mesma estrutura — com **Impacto**, **Probabilidade** e **Severidade** explícitos. Isso permite comparar diferentes análises ao longo do tempo, da mesma forma que um time de segurança usaria uma matriz de risco padronizada em vez de descrições soltas a cada vulnerabilidade encontrada.

## Como o agente decide usar esta skill

O agente aciona esta skill quando a pergunta envolve análise de código, configuração ou infraestrutura em busca de falhas de segurança — termos como "vulnerabilidade", "SQL Injection", "exploração", "pentest" ou "AppSec" no pedido do usuário. Essa decisão é guiada pelo campo `description` do `SKILL.md` e reforçada pela entrada correspondente na tabela de skills do `AGENTS.md`.

## O que esperar na prática

1. Você descreve um código, configuração ou cenário (ex: um `app.py` com SQL Injection, ou um "servidor Ubuntu de laboratório exposto na internet").
2. Antes de sugerir qualquer comando ou ação prática, o agente pergunta o contexto (é laboratório próprio? há autorização? é produção ou desenvolvimento?).
3. Confirmado o contexto, o agente identifica a vulnerabilidade, explica como ela poderia ser explorada (sem fornecer um exploit pronto), referencia a técnica correspondente do MITRE ATT&CK quando aplicável, e classifica a falha no formato padronizado (impacto / probabilidade / severidade).
4. O agente orienta a correção explicando o princípio por trás dela antes de mostrar o código corrigido, e sugere como validar que a correção realmente resolveu o problema.

## Arquivos relacionados

- `skills/vulnerability-analysis/SKILL.md` — roteiro que o agente segue.
- `agent/knowledge/security-basics.md` — base conceitual (vulnerabilidade, ameaça, risco, tríade CIA, boas práticas) que sustenta a análise.
- `agent/persona.md` — trecho que define a postura do agente ao usar esta skill.
- `AGENTS.md` — linha na tabela de skills que indica quando o agente deve acionar esta skill.
