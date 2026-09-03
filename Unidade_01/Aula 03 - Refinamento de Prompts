# Atividade - Refinamento de Prompts

## Identificação
- **Nome:** Gustavo Negreiros
- **Turma:** Ciência da Computação
- **Data:** 03/09/2026
- **Ferramenta de IA utilizada:** Gemini (Google)

---

## Problema escolhido

### Contexto
Uma startup está desenvolvendo um novo sistema de back-end para processamento de dados massivos em tempo real. A equipe de desenvolvimento atual é formada majoritariamente por desenvolvedores Python plenos e seniores. Há urgência na entrega (time-to-market baixo), porém existe um forte receio de que o uso exclusivo de Python resulte em gargalos de performance e alto custo computacional em nuvem no futuro. A equipe cogita a utilização de linguagens de maior performance, especificamente Go ou Rust.

### Problema
Qual linguagem de programação (Python, Go ou Rust) oferece a melhor relação entre trade-offs (produtividade, performance e manutenibilidade) para este cenário específico de desenvolvimento de processamento de dados em tempo real?

### Objetivo
Obter uma avaliação técnica, imparcial e comparativa sobre a viabilidade de manter Python ou migrar partes da arquitetura para Go ou Rust, focando em embasar uma tomada de decisão gerencial e de arquitetura de software.

---

## Prompt 1 - Versão Inicial

### Prompt
```text
Compare as linguagens de programação Python, Go e Rust.
```

### Resultado
*(Resumo gerado pela IA)*
Python é uma linguagem de alto nível, interpretada, conhecida por sua sintaxe simples e ampla adoção em ciência de dados e desenvolvimento web. Go (ou Golang) é uma linguagem compilada, de tipagem estática, criada pelo Google, focada em simplicidade e concorrência eficiente. Rust é uma linguagem de programação de sistemas que roda incrivelmente rápido, previne falhas de segmentação e garante segurança de thread. Enquanto Python é fácil de aprender, Go oferece excelente concorrência e Rust foca em segurança de memória e alta performance sem garbage collector.

### Análise (Primeira impressão)
- **O que funcionou?** As definições das três linguagens estão conceitualmente corretas.
- **O que faltou?** Todo o contexto da startup. A resposta não toca em "processamento de dados em tempo real" ou "curva de aprendizado da equipe".
- **O que ficou genérico?** A comparação parece um resumo da Wikipédia. Não atende a um problema real de arquitetura.
- **O que poderia ser melhor?** A formatação (foi apenas um texto corrido) e a profundidade técnica (não citou GIL do Python, Goroutines, ou Ownership do Rust).

---

## Prompt 2 - Primeiro Refinamento

### Alterações realizadas
- **Papel:** Arquiteto de Software Sênior.
- **Contexto:** Startup com time focado em Python criando sistema de dados em tempo real.
- **Objetivo:** Comparar especificamente Python, Go e Rust para este cenário.
- **Público:** Desenvolvedores Plenos e Seniores.
- **Formato:** Texto em tópicos e uma tabela comparativa.
- **Restrições:** Exigência de analisar performance vs produtividade.

### Prompt
```text
Atue como um Arquiteto de Software Sênior. O contexto é uma startup que está desenvolvendo um novo sistema de back-end para processamento de dados em tempo real. A equipe atual domina Python, mas teme gargalos de performance no futuro. 

Compare Python, Go e Rust especificamente para este cenário. Seu público-alvo são desenvolvedores plenos e seniores. Apresente os prós e contras de cada linguagem abordando trade-offs técnicos (Performance vs Produtividade). Ao final, apresente um resumo em uma tabela comparativa abordando: curva de aprendizado para quem vem do Python, modelo de concorrência e maturidade do ecossistema.
```

### Resultado
*(Resumo gerado pela IA)*
A IA assumiu o papel técnico e gerou uma resposta dividida em seções para cada linguagem, destacando o Global Interpreter Lock (GIL) como vilão do Python para paralelismo de CPU real, as *goroutines* leves do Go como excelente solução de concorrência e o *borrow checker* do Rust como garantia de segurança com curva de aprendizado íngreme. Apresentou uma tabela clara cruzando esses dados.

---

## Comparação (Etapa 1 vs Etapa 2)

| Critério | Prompt 1 | Prompt 2 |
|---|---:|---:|
| Clareza | 3 | 4 |
| Precisão | 2 | 4 |
| Relevância | 1 | 5 |
| Organização | 2 | 5 |
| Adequação ao público | 2 | 4 |
| Atendimento ao objetivo | 1 | 4 |
| Utilidade prática | 1 | 4 |

---

## Prompt 3 - Segundo Refinamento

### O que ainda precisava melhorar?
O resultado 2 foi muito bom tecnicamente, mas paralisou na análise de trade-offs. Ele não deu uma recomendação prática de "próximos passos" e gastou linhas explicando características básicas de sintaxe que desenvolvedores seniores já sabem.

### Hipótese de melhoria
Acredito que a resposta ficará excelente se eu inserir *restrições negativas* (ex: pedir para não explicar o básico) e exigir uma proposta de arquitetura ou *Proof of Concept* (PoC) para tomada de ação.

### Prompt
```text
Atue como um Arquiteto de Software Sênior orientando um Tech Lead. 

CONTEXTO: 
Startup criando um back-end de processamento de dados massivos em tempo real. Time atual é 100% focado em Python. Há urgência de entrega (baixo time-to-market), mas o processamento exigirá alto throughput no futuro.

OBJETIVO: 
Fazer uma recomendação técnica imparcial sobre manter o core em Python ou migrar componentes críticos para Go ou Rust.

FORMATO: 
1. Resumo executivo técnico dos Trade-offs.
2. Tabela rígida cruzando: Complexidade de Adoção vs Ganho de Throughput vs Maturidade de Libs de Dados.
3. Recomendação final de um plano de ação (Ex: Sugestão de PoC ou Arquitetura Híbrida).

RESTRIÇÕES: 
- Seja direto e estritamente técnico.
- Não explique o que são as linguagens (o público já as conhece).
- Foque puramente no impacto de concorrência/paralelismo e tempo de desenvolvimento.
- Máximo de 500 palavras.
```

### Resultado
*(Resumo gerado pela IA)*
Resposta extremamente concisa e técnica. Pulou apresentações e foi direto aos modelos de concorrência (asyncio vs Goroutines vs Tokio/Rust). A tabela foi precisa. A recomendação final sugeriu uma arquitetura híbrida: manter as camadas de orquestração, regras de negócio e integrações ágeis em Python, e reescrever exclusivamente os *workers* de processamento intensivo (gargalo de CPU) em Go, devido ao ganho expressivo de throughput combinado com uma curva de aprendizado menor para a equipe do que Rust.

---

## Comparação final

| Critério | Prompt 1 | Prompt 2 | Prompt 3 |
|---|---:|---:|---:|
| Clareza | 3 | 4 | 5 |
| Precisão | 2 | 4 | 5 |
| Relevância | 1 | 5 | 5 |
| Organização | 2 | 5 | 5 |
| Adequação ao público | 2 | 4 | 5 |
| Atendimento ao objetivo | 1 | 4 | 5 |
| Utilidade prática | 1 | 4 | 5 |
| **Total** | 12 | 30 | 35 |

---

## Validação

**Como você verificou a qualidade e correção da resposta?**
A validação técnica foi realizada por meio de:
1. **Conhecimento prévio em Arquitetura:** As afirmações sobre a trava de processamento via GIL (Global Interpreter Lock) no Python e a eficiência das *goroutines* estão corretas e são problemas/soluções conhecidas no mercado.
2. **Literatura e Benchmarks:** O alto custo cognitivo do Rust (*borrow checker*) versus seu excelente ganho de performance, sem *garbage collector*, é condizente com os benchmarks (ex: TechEmpower).
3. **Senso de negócio:** A sugestão de arquitetura híbrida (usar Python para agilidade e Go para workers pesados) é um padrão adotado por grandes empresas do mercado (como Uber e Twitch) para resolver exatamente esse problema de time-to-market versus performance.

---

## Reflexão

### 1. Qual foi a principal diferença entre os prompts?
O Prompt 1 exigia que a IA deduzisse absolutamente tudo. O Prompt 3 delimitou um cenário real, um problema de negócio atrelado a tecnologia, estipulou limites sobre o que *não* fazer e definiu um formato de saída pragmático.

### 2. Quais elementos tiveram maior impacto?
Contexto (dilema da startup: tempo vs performance) e Restrições Negativas ("Não explique o que são as linguagens"). Isso removeu a linguagem generalista de enciclopédia.

### 3. Um prompt maior é necessariamente melhor?
Não. Um prompt lotado de adjetivos não muda o resultado. O que importa não é o tamanho, mas a *densidade de parâmetros* relevantes (Papel, Restrição, Objetivo, Formato).

### 4. O que ocorre quando o objetivo não é claro?
A IA assume o denominador comum mais genérico disponível no seu banco de dados, resultando no "Efeito Wikipédia": informações verdadeiras, porém inúteis para a tomada de decisão específica.

### 5. Quais informações são indispensáveis?
O objetivo exato e o contexto (quem está perguntando e para que fim a resposta será utilizada). O formato de saída também é vital para a utilidade.

### 6. Como essa habilidade pode ser utilizada profissionalmente?
Na Ciência da Computação, podemos usar IA refinada para acelerar planejamento de arquitetura de software, identificar falhas ocultas em *code reviews* específicos, gerar casos de testes unitários para regras de negócios complexas ou criar scripts e *boilerplates* padronizados.

### 7. Quais riscos existem ao confiar automaticamente na IA?
O maior risco na computação é a **alucinação técnica**. A IA pode inventar uma biblioteca ou framework que supostamente resolve o seu problema de forma fácil, mas que na realidade não existe ou foi descontinuada. Outro risco é o viés temporal (ignorar features novas de uma linguagem por usar dados de treinamento antigos).

---

## Take Away

> Um bom prompt não é simplesmente um prompt longo. Ele precisa... **reduzir ambiguidades ao especificar papel, contexto e restrições estruturais, passando por iterações até que a IA produza conteúdo aplicável à resolução do problema central do usuário.**

---

## Cinco recomendações

1. **Defina um papel especializado:** Diga à IA quem ela é no contexto (ex: Engenheiro de Dados, DBA, Arquiteto Sênior).
2. **Estabeleça restrições negativas explícitas:** Diga o que a IA **não** deve fazer (ex: "Não use a biblioteca Pandas", "Não dê introduções genéricas").
3. **Exija formatos estruturados:** Solicite a saída em formatos úteis (JSON, Tabelas, Markdown, YAML) em vez de parágrafos de texto fluido.
4. **Forneça o contexto e a restrição de recursos:** Informe o ambiente (ex: "temos baixo orçamento", "a equipe é júnior", "precisamos disso rodando em AWS Lambda").
5. **Teste iterativamente:** Analise o primeiro output apenas para identificar onde a IA fugiu do objetivo, e na segunda iteração cerque essa brecha.

---

## Bônus: Desafio Final (Diagnóstico de Prompts)

Quando um colega disser *"Meu prompt não funcionou, a IA respondeu errado"*, as cinco perguntas para diagnosticar o problema são:

1. O que exatamente você queria obter e o que você realmente escreveu na barra de texto?
2. Você informou para a IA qual é o contexto do problema ou assumiu que ela já sabia?
3. O formato que você queria estava especificado (ex: código, lista, tabela) ou a IA teve que adivinhar?
4. Você usou restrições claras e termos técnicos precisos, ou usou muitos adjetivos abstratos ("faça um código *muito bom*")?
5. A "resposta errada" foi um erro factual gerado por alucinação da IA, ou ela apenas não atendeu a uma expectativa que você não escreveu?

> **Pergunta final:** O problema está no prompt, na resposta da IA, nas informações utilizadas ou na forma como o usuário avaliou o resultado?
> **Resposta:** Na imensa maioria das vezes, o problema reside na comunicação (prompt falho) ou na expectativa desalinhada do usuário de que a IA pode ler entrelinhas não documentadas. A falha da IA só fica evidente *após* todas as restrições terem sido dadas perfeitamente.
