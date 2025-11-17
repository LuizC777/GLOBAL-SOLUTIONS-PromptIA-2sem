# Documento de Engenharia de Prompt – Agente de Carreira Adaptativa

## Visão Geral
Este documento descreve a engenharia de prompts utilizada no sistema “Agente de Carreira Adaptativa”, implementado no arquivo `gs2_prompt_ia.py`.  
Cada funcionalidade (F1 a F4) é detalhada com:
- System prompt utilizado
- Estrutura do user prompt esperado
- Estratégia adotada para produzir respostas consistentes

---

# F1 — Análise de Perfil e Risco de Automação

## System Prompt
Peça para o usuário fornecer o trabalho atual dele e suas principais tarefas para estimar o risco de automação e identificar as habilidades mais críticas para o futuro daquela área.


## User Prompt (exemplo utilizado)
Meu trabalho atual é Analista de Suporte em TI. Minhas principais tarefas incluem atendimento a usuários, resolução de incidentes, abertura de chamados e manutenção básica de sistemas. Quero estimar meu risco de automação e saber quais habilidades críticas preciso desenvolver.


## Estratégia
- Direcionar o assistente a solicitar informações profissionais claras.
- Estimar nível de automatização baseado nas tarefas descritas.
- Gerar lista de habilidades críticas para redução de risco de automação.
- Utilizar temperatura baixa para consistência e padrão analítico.

![Image](https://github.com/user-attachments/assets/3ae98ceb-a15f-4090-ae55-8173f38fa912)

---

# F2 — Plano de Upskilling Personalizado

## System Prompt
Com base na profissão e nas habilidades críticas, sugira 3 a 5 áreas de aprimoramento e, para cada uma, sugerir um recurso de aprendizado.


## User Prompt (exemplo utilizado)
Estou buscando evoluir na área de Marketing Digital. Já tenho experiência com mídias sociais e produção de conteúdo, mas quero saber quais habilidades críticas devo aprimorar e receber de 3 a 5 áreas para evoluir, com recomendações de aprendizado para cada uma.


## Estratégia
- Gerar entre 3 e 5 áreas claras de desenvolvimento.
- Cada recomendação deve incluir: área, justificativa e um recurso sugerido.
- Priorizar clareza estrutural e aplicabilidade prática.

![Image](https://github.com/user-attachments/assets/efe17006-eca5-410f-9957-a764f97f79cf)

---

# F3 — Caminho de Reskilling

## System Prompt
Faça uma sugestão de Reskilling ao usuário, para que possa se realocar no mercado de trabalho. Mapeie as habilidades transferíveis e sugira 3 a 5 habilidades novas.


## User Prompt (exemplo utilizado)
Quero migrar da minha área atual de logística para a área de Ciência de Dados. Quais habilidades transferíveis eu já tenho e quais novas devo adquirir? Sugira entre 3 a 5 habilidades novas e um caminho de transição possível.


## Estratégia
- Identificar claramente as habilidades transferíveis da área original.
- Recomendar 3 a 5 habilidades novas necessárias para a área-alvo.
- Definir um caminho de transição estruturado (aprendizado, prática, portfólio).

![Image](https://github.com/user-attachments/assets/2e8f9fe2-b351-4338-bf95-78da0aaee6e1)

---

# F4 — Simulação de Entrevista Backend Júnior

## System Prompt
Faça uma entrevista com o usuário com três perguntas para uma nova função, considerando a clareza relenvacia e profundidade.


## User Prompt (exemplo utilizado)
Quero treinar para uma entrevista para a vaga de Desenvolvedor Backend Júnior. Faça uma pergunta sobre a função e avalie minha resposta.


## Estratégia
- Criar dinâmica de entrevista com perguntas sequenciais.
- Após cada resposta do usuário, avaliar com base em clareza, profundidade e precisão.
- Repetir por três rodadas de interação simulada.

---

# Configurações Gerais do Sistema

## Modelo
gpt-4o-mini


## Temperatura
0.3


## Limite de tokens
max_tokens = 600


## Estrutura das mensagens
messages=[
{"role": "system", "content": sistema},
{"role": "user", "content": mensagem_usuario}
]


---

# Resumo Técnico
O documento descreve a engenharia de prompts aplicada nas quatro funcionalidades, destacando:
- Cada system prompt e sua finalidade específica
- Como o user prompt esperado orienta a interação
- Estratégia textual e estrutural adotada para garantir consistência e resultados analíticos
