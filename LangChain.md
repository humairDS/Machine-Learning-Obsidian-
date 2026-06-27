It is a framework that helps developers build applications powered by LLMs.

LangChain simplifies interaction between LLMs & external data sources or APIs.

Focuses on 
1. Modularity 
2. Compose-ability 
3. Integration.

**Core Idea of LangChain**
"Chain together" multiple LLM calls & components into logical pipelines.

**Core Components** 

==Models==: Interface to LLMs
(e.g. , GPT, Claude, Gemini).

==Prompts==:Define Structured input text for LLMs

==Chains==: Sequence of steps connecting inputs & outputs.

==Agents==: Let LLMs decide which actions or tools to use. 

==Memory==: Retains context or conversation history between interactions.



[[LangChain Practical]] 


## Chains & Pipeline

**Chains**
- Chains are sequence of operations connecting multiple components.
- Enable multi step logic
- Each step passes output to the next. 
- Encourages modular & reusable design.

Types of Chains 
1. Sequential Chains
2. Parallel Chains 
3. Router Chains

Example use:
Summarize or Translate bases on input language

