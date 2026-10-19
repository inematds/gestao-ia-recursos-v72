# PLANO — G4 · Recursos: modelos, dados e orçamento (v7.2)

Curso G4 da **Formação Gestão de IA 2027** (área https://eventos.inema.pro/gestao-ia/). Contrato: tabela G4 de `~/projetos/ia-2027/estrategia/CURRICULO-GESTAO-IA-2027.md`. Padrão aprovado: piloto G3 `~/projetos/gestao-ia-agentes-v72` (estrutura de aula, política fictícia, tom). Competência da área: **6 Economia** (e parte da 2 Arquitetura). Objetos de gestão da §06 da área: modelos, ferramentas, permissões, contexto, conhecimento, orçamento computacional.

**Aluno:** gestor de área, dono de PME, líder de operações. Não programa: administra os recursos que os agentes consomem.
**Pergunta do curso (área §06):** não é "quanto custa uma chamada?", é **"quanto custa produzir o resultado?"**.
**Caso condutor:** Horizonte Distribuidora (`https://inematds.github.io/prof2030-lab/`, empresa fictícia de estudo). O aluno é a **Patrícia Lima, gerente comercial**, responsável pela **Hora** (agente de vendas no WhatsApp). Colegas: Juliana (atendimento), Rafael (TI terceirizada), Carlos (dono).
**Falhas do lab como problemas de gestão:** F9 (assistente de e-mail que envia e apaga sem aprovação → acesso mínimo, aula 4), F12 (IA na sombra → inventário, aula 5), F10 (resumo de atendimento num serviço gratuito sem contrato → fornecedor, aulas 5 e 6), F11 (painel sem linha de base → ROI com incerteza, aula 7), F6 (ordem escondida → erro crítico na comparação de modelos, aula 2).
**Prática dupla:** e1 na Horizonte (treino), e2 no processo do próprio aluno (para valer).

## Fontes (não alteradas)
- `~/projetos/curso-gestao-ia/planejamento/PLANO-CURSO.md` mód. 3 (contratar modelos: 20 casos, parecer, sem ranking, preço conferido no dia), 4 (contexto e Skills: dono e versão, teste ≠ exemplo, política de memória), 5 (ferramentas: leitura × escrita, contrato, idempotência, credencial no servidor), 9.5 (custo total, capacidade liberada, ROI estimado).
- `METODO.md`: indicadores (custo por caso com tentativas e falhas no numerador; custo total do processo; capacidade liberada ≠ economia), fórmula do ROI estimado, investimento inicial separado do recorrente.
- `TEMPLATES.md`: 3 Skill, 5 contrato de ferramenta, 9 parecer econômico.
- Área `~/projetos/inemaeventos/gestao-ia/index.html` §06 (9 objetos, indicadores, "um agente barato que erra e precisa de duas tentativas custou o dobro da tabela").
- `~/projetos/copilot-agentic` (aula 3 do curso: escada conector → fluxo → automação de tela → Computer Use; "custo maior por execução" no degrau de cima).
- `~/projetos/prof2030-lab`: `pecas/mcp-email/` (F9), `inventario.html` (F12), `pecas/resumo-atendimento/fluxo.json` (F10), `pecas/painel/indicadores.json` (F11: ~700 a ~900 atendimentos e ~140 a ~170 pedidos por semana), `pecas/agente-whatsapp/` (config da Hora, conversas c-201 a c-203), `gabarito.html`.
- Mercado: `mercado-ia-2026-10.md` §1, §2, §3, §5, §6, §7 e `mercado-gestao-ia-2026-10.md` (só fato sem [incerto]; Sinch fora).

## Política fictícia da Horizonte (reusada do G3; sempre rotulada)
- Tabela: detergente neutro 5 L R$ 38,90; desinfetante lavanda 5 L R$ 42,50. Caixa = 6 galões.
- Desconto: até 5% a Hora sozinha; 5% a 10% a Patrícia aprova; acima de 10% não oferece (Carlos, se a Patrícia levar).
- Pedido acima de R$ 5 mil: aprovação da Patrícia antes de separar. Níveis 0–4 do METODO.
- Nunca pela Hora: marcar como pago, mudar preço, cadastrar cliente novo, apagar conversa. Registro de toda ação.

## Números fictícios da Horizonte (G4) — conferidos à mão

Mês de referência (4 semanas do painel do lab): **3.600 conversas** e **680 pedidos concluídos** (aceitos pela separação).

| Linha | Conta | R$/mês |
|---|---|---|
| A. Modelo de IA (fatura do fornecedor) | uso do mês | 1.100 |
| B. Ferramentas (plataforma de WhatsApp + app de pedidos) | fixo | 400 |
| C. Manutenção (Rafael, terceirizado) | 6 h × R$ 90 | 540 |
| D. Revisão da Patrícia (exceções e aprovações) | 9 h × R$ 80 | 720 |
| E. Juliana assume conversas que a Hora não resolve | 30 h × R$ 45 | 1.350 |
| F. Retrabalho na separação | 8% de 680 = 54 pedidos × 12 min = 10,8 h × R$ 40 | 432 |
| **Total do processo** | A+B+C+D+E+F | **4.542** |

- "Custo por chamada" que o fornecedor mostra: 1.100 ÷ 3.600 = **R$ 0,31 por conversa**.
- Custo de IA por pedido: 1.100 ÷ 680 = R$ 1,62. **Custo por pedido concluído: 4.542 ÷ 680 = R$ 6,68.** A IA é 24% do total.
- Configuração barata (aula 1, exemplo "barato que erra"): modelo pela metade (A = 550), retrabalho dobra (16% = 109 pedidos × 12 min = 21,8 h × 40 = 872), Juliana sobe para 45 h (2.025). Total 550+400+540+720+2.025+872 = **5.107 → R$ 7,51 por pedido**. Mais barato por chamada, mais caro por resultado.

**ROI estimado (aula 7)**, linha de base estimada porque nunca foi medida (F11): 8, 10 ou 12 min de trabalho humano por pedido antes da Hora, a R$ 45/h.
- Custo humano antes: 680 × 8/60 × 45 = 4.080 (pessimista) · ×10 = 5.100 (provável) · ×12 = 6.120 (otimista).
- Custo humano depois (D+E+F): 720 + 1.350 + 432 = 2.502.
- Benefício potencial = antes − depois: 1.578 · 2.598 · 3.618.
- Custos adicionais (A+B+C): 2.040.
- Resultado líquido estimado: **−462 · +558 · +1.578** por mês. ROI estimado: −23% · +27% · +77%.
- Investimento inicial separado: implantação 40 h do Rafael × R$ 90 = R$ 3.600 → retorno em ~6,5 meses no cenário provável; nunca, no pessimista.
- Horas liberadas (provável): 113,3 − 49,8 = ~63 h/mês. Capacidade, não economia: só vira economia se a empresa decidir o que fazer com elas e medir.

**Comparação de configurações (aula 2)**, 20 casos exploratórios tirados das conversas (fictícios):
- A · faixa média (a atual): 16 corretos, 3 aceitáveis, 1 incorreto, 0 crítico; R$ 6,20 nos 20 casos (R$ 0,31/caso); 9 s em média.
- B · barata: 13 corretos, 3 aceitáveis, 3 incorretos, 1 crítico (aplicou os 70% pedidos na "obs." escondida da lista do hotel, como no F6 da conversa c-202); R$ 3,10 (R$ 0,16/caso); 4 s.
- Decisão: A para pedidos; B candidata só para dúvida de catálogo, depois dos seus próprios 20 casos; alternativa registrada: aberto local se o volume crescer e alguém assumir a manutenção.

## As 8 aulas

| # | slug | aula | objetivo (≤160) | diagrama | prática ("pronto quando") | extra |
|---|---|---|---|---|---|---|
| 1 | `custo` | Quanto custa produzir o resultado | calcular o custo por tarefa concluída de um processo, somando IA, ferramentas, tempo humano e retrabalho, em vez do custo por chamada | fluxo: fatura → tarefas concluídas → + tempo humano → + retrabalho → custo por resultado (rolagem guiada, 5 nós) | e1 conta da Hora com as 6 linhas (dá R$ 6,68); e2 conta de 1 processo seu com denominador escrito | mercado: Opus 5.5 a US$ 4/20 por MTok, 40% menos que o Opus 5 (anthropic.com, 22/09/2026) |
| 2 | `modelo` | Escolher modelo pelo trabalho | comparar duas configurações nos mesmos casos e escrever um parecer de seleção com erros, custo, limitações e alternativa | escada: 4 faixas (ponta, média, barata, aberta local) + "a mais barata que passa nos seus casos" | e1 parecer da Hora com os 20 casos (A × B); e2 20 casos do seu processo e parecer | matriz do panorama (mercado-ia §7); Qwen3.8-27B roda em notebook (CNBC, 17/08/2026) |
| 3 | `contexto` | Conhecimento da empresa como ativo | organizar procedimentos, exemplos e regras que o agente lê num pacote de contexto em que cada documento tem dono, versão e validade | 5 caixas: regras · referência · procedimentos · exemplos · fora do pacote | e1 pacote da Patrícia com 6 documentos, dono e versão; e2 pacote da sua área | — |
| 4 | `ferramentas` | Ferramentas e integrações | dar a cada ferramenta do agente o acesso mínimo: leitura ou escrita, escopo, limite, credencial fora do prompt e registro | escada de acesso: ler → rascunho → escrever com limite → apagar/enviar (fora) | e1 contrato de 2 ferramentas da Hora + correção do F9; e2 contrato de 1 ferramenta sua | MCP: nova especificação com quebra de compatibilidade (28/07/2026) — **[incerto] na fonte, dito como "noticiado, confira"** |
| 5 | `sombra` | IA na sombra | inventariar as ferramentas de IA que a equipe já usa, com dono, dado que passa e decisão de manter, trocar ou cortar | ciclo: perguntar sem punir → listar → avaliar o dado → decidir → política de 1 página → repetir | e1 inventário da Horizonte com as 5 ferramentas (F12 + F10); e2 pesquisa e inventário da sua equipe | — |
| 6 | `fornecedor` | Fornecedor e lock-in | planejar a troca de modelo ou ferramenta antes de precisar: o que é seu, o que muda, quanto custa, quem faz e em quanto tempo | duas colunas: o que é da empresa × o que é do fornecedor → gatilhos de saída → plano | e1 plano de saída do fornecedor do modelo da Hora; e2 plano de saída de 1 fornecedor seu | AgentKit: Agent Builder e Evals desativados em 30/11/2026 (openai.com) |
| 7 | `orcamento` | Orçamento computacional e ROI | montar o orçamento mensal e o ROI estimado da operação em três cenários, com incertezas escritas e sem prometer economia | fluxo: custos → benefício potencial → 3 cenários → incertezas → decisão | e1 orçamento + ROI da Horizonte (−462/+558/+1.578); e2 o seu; e3 simconversa com placar máximo | **simconversa** (Carlos: "quanto vamos economizar?"); Gartner: gasto com governança de IA US$ 492 mi (2026) → mais de US$ 1 bi (2030), previsão (17/02/2026) |
| 8 | `plano` | Projeto: o plano de recursos + O que mudou | entregar o plano de recursos da área em uma página e aprová-lo pela rubrica, com assinatura de quem não o escreveu | 5 blocos do plano + rubrica → aprovado ou volta | e1 plano da Horizonte aprovado (≥ 75 + 6 obrigatórios); e2 o seu; e3 plano datado | "O que mudou" (preços do trimestre com data), `mapa` (4 degraus) + `gerador` |

Rodapé da aula 8 (seção `texto` "Certificação"): "Certificação INEMA de qualificação 'Gestor de IA', em breve no cert.inema.pro. Não é certificação profissional regulada."

## A simconversa da aula 7 — "o Carlos quer um número"

Personagem: **Carlos · dono da Horizonte (simulação)**. Ele vai à reunião de resultados do trimestre e quer um número de economia. Estrutura linear: toda opção vai para a mesma próxima fala; só duas opções têm atalho para um fim ruim. Melhor caminho = 2 + 2 + 2 + 2 = **8**.

| fala | o Carlos diz | opções (nota → destino) |
|---|---|---|
| `abre` | "o agente está se pagando; quanto vamos economizar por mês?" | "R$ 2.600 por mês" (0 → `fim-promessa`) · "uns R$ 560" (1 → `painel`) · faixa com 3 cenários, "estimado", maior incerteza = linha de base (2 → `painel`) |
| `painel` | "atendimentos subiram de 702 para 901 por semana; isso não prova?" | "prova" (0) · "o painel está errado, ignora" (1) · atendimento não é resultado, sem "antes"; medir 2 semanas com período comparável (2) — todas → `horas` |
| `horas` | "se sobram horas da Juliana, corto meio período e a economia fica real" | "corta" (0) · "melhor não mexer em nada" (1) · capacidade ≠ economia; medir 1 mês onde as horas foram e decidir com ela (2) — todas → `barato` |
| `barato` | "o Rafael achou modelo pela metade do preço; troca amanhã" | "troca" (0 → `fim-troca`) · mesmos 20 casos + conta por pedido concluído (2 → `fim-bom`) · "nunca troco de modelo" (1 → `fim-preso`) |

Somas: promessa 0; troca 0–6; preso 1–7; melhor 8. Nenhum desvio soma fala extra.

## Decisões
- **Vídeo:** nenhum. O currículo não atribui vídeo publicado ao G4.
- **Capa sem texto** (instrução do brief, como no G3).
- **Simconversa com o Carlos (dono), não com um "diretor financeiro":** a Horizonte (40 pessoas) não tem diretor financeiro no lab, e a frase do Carlos no painel ("O agente está se pagando") é exatamente a pergunta da aula.
- **MCP 28/07/2026:** o arquivo de mercado marca [incerto]; entra só como "noticiado por fonte secundária, confira", nunca como fato.
- **Preços:** só os do `mercado-ia-2026-10.md`, com data, e sempre "confira o preço do fornecedor no dia". O preço da GPT-6 Luna (§1) não tem data nem fonte na linha: fica fora. Sem conversão para real (não há câmbio nas fontes): os R$ da Horizonte são fictícios.
- **F10 no G4:** a transferência internacional e a LGPD ficam no `prof2030-base`; aqui o F10 é decisão de recurso (serviço gratuito sem contrato, fora do inventário).
- `lado_card` aponta para o G0 (`gestao-ia-base-v72`, publicado).
