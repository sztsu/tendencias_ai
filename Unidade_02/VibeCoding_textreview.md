# Atividade: Programação Assistida por Inteligência Artificial
**Instituição:** UDF - Centro Universitário

## 1. Evidências da Leitura
Do artigo sobre *vibe coding*, chamaram-me à atenção duas ideias principais:
* A IA não retira a necessidade de saber programar, apenas muda o foco. Em vez de escrever o código todo à mão, passamos a orientar e rever o trabalho da máquina.
* Não podemos confiar cegamente. A confiança ganha-se testando aos poucos e verificando o código de forma contínua.

---

## 2. Questões Norteadoras

**1. Até que ponto podemos confiar no código produzido pela IA?**
A confiança tem de vir da revisão, nunca de uma aceitação cega. É crucial verificar as alterações (*diffs*), as chamadas de API e cruzar tudo com a documentação oficial para evitar "alucinações" do modelo e código mal estruturado.

**2. A IA reduz a necessidade de conhecimento em programação ou transforma o tipo de conhecimento necessário?**
Transforma completamente. Em vez de focarmos na sintaxe linha a linha, atuamos mais como arquitetos e revisores. O nosso conhecimento passa a ser usado para avaliar o que foi gerado, gerir o contexto que damos à IA e saber a hora certa de assumir o controlo manual.

**3. Quando é melhor utilizar a IA e quando é melhor assumir o controlo manualmente?**
Vale mais a pena ir para o manual quando o tempo gasto a tentar criar o *prompt* perfeito é maior do que fazer a alteração diretamente. O trabalho manual também é melhor para resolver *bugs* complexos ou quando a IA não consegue acertar num detalhe específico após algumas tentativas.

---

## 3. Estudo de Caso

* **Ações da equipa:** Antes de juntar o código ao projeto principal, a equipa devia analisar atentamente o que foi gerado, confirmar se as bibliotecas sugeridas fazem sentido para a arquitetura atual e fazer testes que vão além do cenário ideal.
* **Responsabilidades humanas:** A máquina não entende as regras de negócio, a arquitetura geral nem as políticas de segurança. Logo, a responsabilidade de garantir que o código tem qualidade e pode ser mantido a longo prazo continua a ser 100% da equipa.

---

## 4. Síntese e Boas Práticas

**Boas Práticas:**
1. Nunca usar o botão "Accept All" sem ler; rever sempre os *diffs* com atenção.
2. Fazer *prompts* mais curtos e objetivos, resolvendo um problema de cada vez para evitar que a IA se perca.
3. Saber o momento de parar de "brigar" com a IA e fazer correções mais complexas à mão.

**Síntese Final:**
Programar com IA de maneira responsável não significa apenas saber pedir código; significa também assumir o papel de revisor de qualidade. Exige usar o nosso conhecimento técnico para validar a segurança e evitar ganhar débito técnico no projeto. A IA é um excelente assistente que acelera o processo, mas a palavra final sobre a arquitetura e sobre o que vai para produção tem de ser sempre humana.