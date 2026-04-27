
# **Projeto:** [LookDay]
### **Problema que resolve:**
O Look Day é um sistema simples que sugere a roupa ideal para o dia com base nas condições climáticas da cidade informada pelo usuário. O objetivo é facilitar decisões do dia a dia, utilizando dados externos e uma lógica inteligente de recomendação.

## Integrantes
| Nome | GitHub |
|------|--------|
| [Breno de Arruda Ferro] | [@euFerro] |
| [Lucas Facini] | [@LucasFacini01] |
| [Murilo Boschiero] | [@7JustAguy7] |

## Arquitetura

```mermaid
---
config:
  layout: elk
---
flowchart TD
    subgraph Frontend[" Frontend do Projeto"]
        A[" Usuário digita cidade"]
        B[" Interface coleta entrada"]
    end

    subgraph Backend[" Backend / n8n Workflow"]
        C[" HTTP Request (PositionStack)<br/>→ Coordenadas da cidade"]
        D[" HTTP Request (WeatherStack)<br/>→ Dados de clima atuais"]
        E[" IA - Google Gemini<br/>→ Sugestão de roupa com base no clima"]
        F[" Resposta formatada<br/>→ JSON com look completo"]
    end

    subgraph Output[" Resultado para o usuário"]
        G[" Exibição na tela"]
        H[" Notificação ao usuário"]
    end

    A --> B --> C
    C --> D --> E --> F --> G --> H

    classDef indigo stroke:#818cf8,fill:#eef2ff;
    classDef cyan stroke:#22d3ee,fill:#ecfeff;
    classDef sky stroke:#38bdf8,fill:#f0f9ff;
    classDef violet stroke:#a78bfa,fill:#f5f3ff;
    classDef fuchsia stroke:#e879f9,fill:#fdf4ff;
    classDef yellow stroke:#facc15,fill:#fefce8;
    classDef orange stroke:#fb923c,fill:#fff7ed;
    classDef green stroke:#4ade80,fill:#f0fdf4;

    class Frontend indigo;
    class Backend sky;
    class Output orange;

    class A,B indigo;
    class C,D sky;
    class E fuchsia;
    class F yellow;
    class G,H orange;
```
⸻

Objetivo

Ajudar o usuário a escolher o que vestir diariamente com base na temperatura e condição do tempo.

⸻

Funcionalidades
	•	Entrada de cidade pelo usuário
	•	Consulta de clima em tempo real
	•	Sugestão automática de roupa baseada no clima
	•	Notificação com recomendação do dia

⸻

Tecnologias Utilizadas
	•	Frontend:
	•	Backend:
	•	API externa: PositionStack / WeatherStack API
	•	IA: Lógica simples de decisão baseada em temperatura e clima

⸻

Como Funciona
	1.	O usuário informa a cidade
	2.	O sistema consulta a API de clima
	3.	A IA interpreta os dados (temperatura e condição)
	4.	O sistema gera uma sugestão de roupa
	5.	O usuário recebe uma notificação com a recomendação

⸻

Exemplo de Regras
	•	Temperatura abaixo de 15°C → Casaco
	•	Entre 15°C e 25°C → Roupa leve
	•	Acima de 25°C → Roupa fresca
	•	Se estiver chovendo → Levar guarda-chuva

⸻

Integrações
	•	API de clima (PositionStack / WeatherStack)
	•	Sistema de notificação (alerta na aplicação ou navegador)

⸻

Status do Projeto

Em desenvolvimento – Atividade 5 e 6: Github e Fluxo N8N com Gemini.
