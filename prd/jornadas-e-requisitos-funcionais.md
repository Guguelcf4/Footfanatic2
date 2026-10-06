# Jornadas da aplicação e requisitos funcionais — FutFonic

> **Status:** Rascunho para validação de produto
> **Escopo:** Jornadas e requisitos derivados das personas Torcedor, Investidor e Administrador
> **Tecnologias:** Não definidas

## 1. Objetivo e escopo

Este documento transforma os objetivos, tarefas, necessidades e funcionalidades prioritárias descritos nas personas do FutFonic em jornadas de ponta a ponta e requisitos funcionais. Cada jornada considera o que a pessoa faz na interface e o que a aplicação precisa consultar, validar, organizar ou atualizar no backend, sem prescrever tecnologias.

As três personas fazem parte desta rodada. Cada uma tem uma área de uso adequada ao seu papel; o backend deve aplicar as permissões independentemente do que a interface exibe. Isso não define como autenticação ou concessão de acesso será implementada.

As prioridades são relativas a cada persona, e não uma priorização única do produto:

- **P0:** capacidade explicitamente prioritária para a persona ou necessária para seu objetivo principal.
- **P1:** necessidade explicitamente descrita, mas secundária em relação às prioridades da persona.

Os requisitos não criam fontes de dados, fórmulas de indicadores, regras de negócio ou garantias de atualização que não estejam nas personas. Pontos sem definição estão registrados em **Questões em aberto**.

## 2. Fontes

- [Persona Torcedor](./personas/torcedor.md)
- [Persona Investidor](./personas/investidor.md)
- [Persona Administrador](./personas/administrador.md)
- [Personas do FutFonic](./futfonic-personas.md)
- Decisões de escopo confirmadas nesta conversa: mapear as três personas; representar áreas e permissões separadas por perfil; registrar o escopo descrito pelas personas, priorizado por perfil; não definir tecnologias.

## 3. Jornadas

### 3.1 Torcedor — acompanhar o time e entender seu momento

**Objetivo:** encontrar em um só lugar a situação do time, o contexto do campeonato, notícias e desempenho recente.

1. **Abrir a área de acompanhamento**
   - **Interface:** apresenta um caminho direto para escolher ou consultar um time e acessar seu resumo.
   - **Backend:** disponibiliza os dados disponíveis do time selecionado e os relacionamentos necessários com competição, partidas, notícias e estatísticas.
2. **Ver o resumo do time**
   - **Interface:** organiza posição na tabela, resultados recentes, próximos jogos, notícias e indicadores do time.
   - **Backend:** reúne os dados correspondentes e informa indisponibilidade ou atualização incompleta em vez de apresentar dados ausentes como atuais.
3. **Entender o contexto da rodada**
   - **Interface:** permite consultar classificação, resultados e próximos jogos da competição e navegar para os detalhes relevantes.
   - **Backend:** retorna classificação e partidas da competição selecionada, preservando a relação entre time, rodada e partida.
4. **Investigar uma notícia ou ocorrência**
   - **Interface:** permite encontrar notícias relacionadas ao time ou à competição, incluindo temas como contratações e lesões quando publicados.
   - **Backend:** fornece conteúdo e seus dados editoriais disponíveis; não inventa uma notícia ou ocorrência quando não há registro.
5. **Avaliar jogadores ou desempenho**
   - **Interface:** mostra estatísticas individuais e coletivas em linguagem clara e permite comparar jogadores ou times.
   - **Backend:** retorna as métricas dos itens selecionados em bases comparáveis e explicita quando alguma métrica não está disponível.
6. **Retornar após uma rodada**
   - **Interface:** facilita rever o histórico recente e identificar mudanças de desempenho.
   - **Backend:** disponibiliza resultados e histórico existentes para o período consultado.

**Resultado esperado:** o torcedor entende a posição, o desempenho recente, os próximos jogos e as notícias relevantes sem precisar reunir essas informações em fontes dispersas.

### 3.2 Administradora — manter conteúdo, dados e operação confiáveis

**Objetivo:** detectar problemas, administrar os acessos e manter corretos os dados e conteúdos apresentados na plataforma.

1. **Acessar a área administrativa autorizada**
   - **Interface:** apresenta ferramentas administrativas apenas para um perfil com permissão correspondente.
   - **Backend:** valida a permissão em cada operação administrativa e não confia apenas na ocultação de elementos da interface.
2. **Verificar o estado operacional**
   - **Interface:** consolida indicadores de uso, falhas, conteúdo pendente e situação das atualizações ou integrações.
   - **Backend:** disponibiliza os estados e registros existentes para que problemas e atualizações incompletas possam ser identificados.
3. **Administrar usuários e permissões**
   - **Interface:** permite consultar usuários e seus níveis de acesso e executar ações autorizadas de gestão.
   - **Backend:** valida as permissões do operador e aplica as alterações de acesso solicitadas.
4. **Revisar e gerir conteúdo**
   - **Interface:** permite localizar conteúdo pendente ou publicado, revisar seus dados e executar as ações de moderação permitidas.
   - **Backend:** mantém o estado do conteúdo e disponibiliza para a área pública apenas conteúdo liberado para publicação.
5. **Manter dados esportivos**
   - **Interface:** permite cadastrar e atualizar competições, times e jogadores e revisar inconsistências identificadas.
   - **Backend:** valida os dados recebidos e apresenta conflitos ou dados inválidos para correção, sem substituir silenciosamente informações conflitantes.
6. **Investigar falhas ou atualizações incompletas**
   - **Interface:** permite consultar erros, registros operacionais e estados das integrações e atualizações de conteúdo.
   - **Backend:** expõe os registros e estados disponíveis para localizar a falha e apoiar sua correção.
7. **Acompanhar indicadores operacionais**
   - **Interface:** apresenta relatórios de uso e operação para os períodos e dimensões disponíveis.
   - **Backend:** fornece os dados operacionais correspondentes sem misturá-los com métricas de negócio não definidas.

**Resultado esperado:** a administradora consegue identificar e tratar problemas de acesso, conteúdo, integridade de dados e atualização da plataforma.

### 3.3 Investidor — avaliar crescimento, engajamento e potencial de negócio

**Objetivo:** avaliar a relevância e a evolução da plataforma com indicadores claros, comparáveis e organizados por período e segmento.

1. **Acessar a área executiva autorizada**
   - **Interface:** apresenta uma visão executiva para um perfil com permissão correspondente.
   - **Backend:** valida a permissão antes de fornecer indicadores de negócio e audiência.
2. **Consultar os indicadores gerais**
   - **Interface:** apresenta KPIs de usuários ativos, crescimento, retenção, frequência e engajamento, conforme os dados disponíveis.
   - **Backend:** fornece os dados de cada indicador com seu período e dimensão, sem tratar ausência de dados como valor zero.
3. **Segmentar a audiência e o conteúdo**
   - **Interface:** permite filtrar os relatórios por período, time, jogador, campeonato, categoria de conteúdo, perfil de usuário, região e interesse, quando disponíveis.
   - **Backend:** aplica os filtros selecionados de forma consistente aos dados e informa quando um segmento não possui dados.
4. **Comparar resultados**
   - **Interface:** permite comparar períodos, times, campeonatos ou conteúdos e visualizar tendências relevantes; benchmarks de mercado aparecem quando houver referência aprovada.
   - **Backend:** retorna dados comparáveis para os recortes selecionados e identifica os períodos abrangidos; só fornece benchmarks com fonte e metodologia aprovadas.
5. **Analisar conteúdo e campanhas**
   - **Interface:** permite examinar visualizações, interações e compartilhamentos de conteúdos e consultar resultados de campanhas quando existirem dados associados.
   - **Backend:** relaciona os indicadores de conteúdo e campanha somente quando houver dados registrados para essa relação.
6. **Avaliar oportunidades de monetização**
   - **Interface:** oferece a informação disponível sobre audiência, conteúdo, publicidade e patrocínio para apoiar a avaliação de oportunidades.
   - **Backend:** disponibiliza os dados existentes sem apresentar projeções, conversões ou retorno financeiro como fatos quando suas regras e fontes não tiverem sido definidas.

**Resultado esperado:** o investidor consegue examinar crescimento, retenção, engajamento e relevância de segmentos com contexto suficiente para apoiar decisões de negócio.

## 4. Requisitos funcionais

### 4.1 Torcedor

| ID | Prioridade | Requisito | Interface | Backend | Critério de aceite |
|---|---|---|---|---|---|
| FR-01 | P0 | A aplicação deve oferecer uma visão consolidada do time selecionado. | Exibe posição, desempenho recente, próximos jogos, notícias e estatísticas disponíveis em uma área de acompanhamento. | Reúne os dados vinculados ao time e informa quando uma categoria de dado estiver indisponível ou desatualizada. | Ao consultar um time, a pessoa consegue distinguir os dados disponíveis dos indisponíveis e navegar para seus detalhes. |
| FR-02 | P0 | A aplicação deve permitir consultar a classificação de uma competição. | Exibe a tabela e permite localizar o time e sua posição. | Fornece a classificação da competição e os dados associados a cada time. | Ao selecionar uma competição, a classificação apresentada corresponde a essa competição e identifica a posição do time consultado. |
| FR-03 | P0 | A aplicação deve permitir consultar resultados recentes e próximos jogos de um time ou competição. | Lista partidas e permite abrir seus detalhes disponíveis. | Fornece as partidas, resultados e detalhes registrados para o filtro selecionado. | A lista distingue partidas já realizadas das próximas e não apresenta resultado inexistente como confirmado. |
| FR-04 | P0 | A aplicação deve permitir localizar notícias relacionadas a times e competições. | Apresenta e organiza notícias relevantes por time ou competição e permite abrir o conteúdo. | Fornece o conteúdo editorial relacionado aos filtros; informações como contratações e lesões só aparecem quando disponíveis no conteúdo ou dado associado. | Ao filtrar por time ou competição, os resultados exibidos correspondem ao filtro e uma busca sem resultados é comunicada claramente. |
| FR-05 | P0 | A aplicação deve apresentar estatísticas individuais e coletivas de jogadores e times. | Exibe métricas e contexto de forma compreensível para consulta do torcedor. | Fornece as métricas disponíveis para o jogador, time ou período consultado. | A pessoa consegue identificar a quem e a qual recorte temporal cada estatística se refere; métricas indisponíveis não são exibidas como zero. |
| FR-06 | P0 | A aplicação deve permitir comparar jogadores ou times. | Permite selecionar os itens a comparar e apresenta suas métricas lado a lado. | Retorna métricas correspondentes aos itens selecionados e sinaliza diferenças de disponibilidade. | A comparação identifica cada item e não sugere equivalência quando as métricas ou recortes não forem comparáveis. |
| FR-07 | P1 | A aplicação deve permitir consultar a evolução recente do desempenho de um time. | Apresenta resultados e indicadores históricos disponíveis em sequência temporal. | Fornece histórico para o período consultado. | A visualização permite reconhecer o período e a sequência dos dados apresentados. |
| FR-08 | P1 | A aplicação deve permitir consultar informações disponíveis sobre escalações, lesões e suspensões relacionadas a uma partida ou time. | Apresenta as informações junto ao contexto esportivo correspondente. | Fornece somente registros existentes e sinaliza quando não há informação disponível. | Ausência de informação não é interpretada como confirmação de que não há lesões, suspensões ou alterações de escalação. |

### 4.2 Administradora

| ID | Prioridade | Requisito | Interface | Backend | Critério de aceite |
|---|---|---|---|---|---|
| FR-09 | P0 | A aplicação deve separar as áreas e operações administrativas por permissão. | Exibe ações administrativas de acordo com o perfil autorizado. | Verifica a permissão em cada operação administrativa, inclusive quando a ação não parte da interface prevista. | Um perfil sem permissão não consegue consultar ou executar uma operação administrativa protegida. |
| FR-10 | P0 | A aplicação deve permitir gerir usuários e seus níveis de acesso. | Permite consultar usuários e realizar as ações de gestão autorizadas. | Valida a permissão do operador e aplica alterações de usuário ou acesso conforme regras autorizadas. | Uma alteração de acesso só é concluída quando autorizada; caso contrário, a aplicação informa que a ação não foi permitida. |
| FR-11 | P0 | A aplicação deve permitir gerir conteúdo e seu estado de moderação/publicação. | Permite localizar conteúdo pendente ou publicado, revisar e executar ações disponíveis de moderação. | Mantém o estado do conteúdo e impede que conteúdo não liberado seja disponibilizado como publicado. | Conteúdo pendente não aparece como publicado; após ação autorizada, o estado resultante é apresentado de forma consistente. |
| FR-12 | P0 | A aplicação deve permitir cadastrar e atualizar competições, times e jogadores. | Disponibiliza formulários e consultas para gestão dessas entidades. | Valida os dados recebidos e persiste alterações válidas, apresentando erros de validação sem ocultá-los. | Uma alteração válida pode ser consultada após o salvamento; dados inválidos retornam indicação do problema e não são tratados como salvos. |
| FR-13 | P0 | A aplicação deve apoiar a verificação de integridade dos dados esportivos e editoriais. | Apresenta dados inconsistentes identificados e permite localizar o registro para correção. | Detecta ou recebe os problemas de consistência que as regras de domínio venham a definir e os associa aos registros pertinentes. | Quando uma inconsistência definida pelas regras existentes for identificada, a administradora consegue localizar o registro e ver o problema. |
| FR-14 | P0 | A aplicação deve apresentar estados de atualização de conteúdo e integrações de dados disponíveis para operação. | Exibe o estado e os problemas conhecidos de atualizações e integrações. | Disponibiliza os estados e erros registrados, sem indicar sucesso para uma atualização que falhou ou não foi concluída. | A administradora consegue distinguir uma atualização concluída de uma falha, pendência ou estado desconhecido. |
| FR-15 | P0 | A aplicação deve oferecer visão administrativa de uso e saúde operacional. | Apresenta indicadores de uso, erros e falhas em uma visão consolidada. | Fornece os indicadores e registros operacionais disponíveis para consulta. | A visão permite consultar os indicadores existentes e identificar explicitamente quando um dado operacional não está disponível. |
| FR-16 | P1 | A aplicação deve permitir consultar relatórios operacionais por período. | Permite selecionar um período e visualizar os dados operacionais disponíveis. | Aplica o período selecionado aos dados retornados. | Os resultados identificam o período consultado e não incluem registros fora dele. |

### 4.3 Investidor

| ID | Prioridade | Requisito | Interface | Backend | Critério de aceite |
|---|---|---|---|---|---|
| FR-17 | P0 | A aplicação deve separar o acesso aos indicadores executivos por permissão. | Exibe a área executiva para um perfil autorizado. | Verifica a permissão antes de fornecer os indicadores e relatórios executivos. | Um perfil sem permissão não consegue consultar os indicadores protegidos. |
| FR-18 | P0 | A aplicação deve apresentar indicadores de usuários ativos e crescimento por período. | Exibe valores e evolução para os períodos disponíveis. | Fornece os dados associados ao período solicitado e distingue ausência de dados de valor zero. | A pessoa consegue identificar o período de cada indicador e diferenciar zero de dado indisponível. |
| FR-19 | P0 | A aplicação deve apresentar indicadores de retenção, frequência e engajamento. | Exibe os indicadores com contexto suficiente para interpretação. | Fornece valores e recortes disponíveis, respeitando as definições de métrica que forem aprovadas. | Cada indicador apresentado informa o período e a segmentação a que se refere; itens sem definição aprovada ficam fora de resultados definitivos. |
| FR-20 | P0 | A aplicação deve permitir segmentar relatórios por período, time, jogador, campeonato e categoria de conteúdo. | Disponibiliza filtros para essas dimensões e reflete os filtros ativos no relatório. | Aplica os mesmos filtros aos dados do relatório e informa quando a combinação não possui dados. | Alterar um filtro atualiza o recorte apresentado sem misturar dados de outro recorte. |
| FR-21 | P0 | A aplicação deve permitir analisar audiência por perfil, região e interesse esportivo quando esses dados estiverem disponíveis. | Apresenta os recortes disponíveis e indica quando uma dimensão não pode ser consultada. | Fornece apenas os dados registrados para cada dimensão. | O relatório não apresenta segmentos sem dados como se representassem toda a audiência. |
| FR-22 | P0 | A aplicação deve permitir analisar desempenho de conteúdos por visualizações, interações e compartilhamentos. | Lista ou compara conteúdos segundo as métricas disponíveis. | Fornece métricas associadas ao conteúdo e ao período selecionados. | A pessoa consegue identificar o conteúdo, período e métrica usados em cada resultado. |
| FR-23 | P0 | A aplicação deve permitir comparar indicadores entre períodos ou segmentos. | Apresenta os recortes lado a lado ou em uma visualização comparativa identificada. | Retorna os dados correspondentes a cada recorte sem misturar períodos ou dimensões. | Cada lado da comparação identifica seu recorte; comparações sem dados compatíveis são sinalizadas como indisponíveis. |
| FR-24 | P1 | A aplicação deve permitir avaliar o desempenho de campanhas, publicidade e patrocínios com base nos dados disponíveis. | Apresenta resultados associados a campanhas ou oportunidades registradas. | Relaciona campanha e audiência somente quando essa relação estiver suportada pelos dados e definições aprovados. | A tela distingue resultado observado de dado ausente e não apresenta retorno ou conversão calculados sem definição aprovada. |
| FR-25 | P1 | A aplicação deve permitir examinar a relevância relativa de times, jogadores, campeonatos e conteúdos. | Exibe comparações ou ordenações nos recortes selecionados. | Calcula ou fornece as métricas correspondentes conforme definições aprovadas. | A ordenação identifica a métrica, o período e o recorte usados para determinar relevância. |
| FR-26 | P1 | A aplicação deve permitir comparar indicadores da plataforma com benchmarks de mercado aprovados. | Apresenta a comparação e identifica a referência de mercado usada. | Fornece benchmarks somente quando houver fonte e metodologia aprovadas e comparáveis ao indicador consultado. | Sem benchmark aprovado ou comparável, a aplicação informa que a comparação não está disponível. |

## 5. Regras transversais de interação

As seguintes regras orientam a experiência de interface e as respostas do backend em todas as jornadas:

1. A interface deve distinguir carregamento, ausência de resultados, indisponibilidade e erro, sem apresentar estados de falha como sucesso.
2. Os dados exibidos devem conservar seu contexto de time, competição, período, conteúdo ou segmento, conforme aplicável.
3. Uma operação administrativa ou executiva protegida deve ser autorizada pelo backend; esconder uma opção na interface, por si só, não concede proteção.
4. Alterações e filtros devem indicar o resultado efetivamente retornado pelo backend; erros de validação ou permissão devem ser apresentados de forma compreensível.
5. As personas pedem informação clara e confiável, mas não definem limites numéricos de latência, atualização, disponibilidade ou retenção de dados. Esses limites não são fixados aqui.

## 6. Questões em aberto

| ID | Questão | Impacto |
|---|---|---|
| OQ-01 | Quais são as fontes oficiais para classificação, partidas, estatísticas, escalações, lesões, suspensões e notícias? | Define cobertura, atribuição e validação dos dados exibidos ao torcedor. |
| OQ-02 | O que “em tempo real” significa para cada tipo de dado: atualização durante a partida, após a partida ou em outro intervalo? | Impede definir frequência de atualização e critérios de atualidade sem validação. |
| OQ-03 | O torcedor terá conta e poderá salvar time favorito e preferências, ou escolherá o time a cada visita? | Afeta personalização, persistência de preferências e etapas de acesso. |
| OQ-04 | Quais são as fórmulas, janelas temporais e definições de usuários ativos, crescimento, retenção, frequência e engajamento? | Necessário para que relatórios executivos sejam comparáveis e confiáveis. |
| OQ-05 | Quais dados e regras associam audiência a campanhas, publicidade, patrocínio, conversão ou receita? | Define o que pode ser apresentado como resultado observado ou oportunidade de monetização. |
| OQ-06 | Quais perfis administrativos e executivos existem, e quais operações cada perfil pode executar? | Necessário para estabelecer a matriz de permissões completa. |
| OQ-07 | Quais são os estados permitidos para conteúdo e o fluxo de revisão, aprovação, publicação e retirada? | Necessário para detalhar as transições do fluxo editorial. |
| OQ-08 | Quais regras identificam duplicidade ou inconsistência em times, jogadores, competições e estatísticas? | Necessário para tornar a validação de integridade objetiva e verificável. |
| OQ-09 | Existem benchmarks externos aprovados para comparação de mercado? Em caso afirmativo, quais são a fonte e a metodologia? | A persona investidora cita benchmarks, mas nenhuma fonte ou regra de comparação está definida. |
| OQ-10 | Quais dimensões de audiência podem ser coletadas e apresentadas, e quais limites de privacidade devem ser observados? | Afeta segmentação por perfil, região e interesse. |
| OQ-11 | Quais são os limites desejados para tempo de resposta, disponibilidade e atraso máximo dos dados? | Permite transformar expectativas de rapidez e confiabilidade em critérios não funcionais mensuráveis. |

## 7. Fora de escopo desta definição

- Escolha de tecnologias, arquitetura técnica, provedores ou integrações específicas.
- Definição de fórmulas, fontes externas, frequência de atualização ou metas quantitativas ainda não aprovadas.
- Definição de autenticação, cadastro do torcedor, persistência de preferências ou matriz detalhada de permissões.
- Projeções financeiras ou recomendações automáticas de investimento/monetização sem dados e regras aprovados.
