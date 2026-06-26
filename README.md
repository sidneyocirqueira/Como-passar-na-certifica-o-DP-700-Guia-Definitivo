# Guia de Estudos — Certificação DP-700 (Microsoft Fabric Data Engineer)

> Material baseado na live "Data Days" sobre como estudar e passar na certificação **DP-700**.
> Apresentador: Sidney Cirqueira — Cloud Solution Architect na Microsoft, Fabric Day Insider (Top Contributor FY26).

---

## 📌 Sobre o programa Data Days

O **Data Days - 60 dias** é um programa que visa capacitar a comunidade técnica com muito conteúdo sobre as certificações **DP-600**, **DP-700** e **DP-800**, com apoio do Microsoft Reactor e de diversos MVPs/MCTs (Alison Pezzott, Luiz Santana, Paulo Grijó, entre outros). O evento acontece em vários idiomas (espanhol, inglês e português) e reúne conteúdo sobre:

- Certificações **DP-600**, **DP-700** e **DP-800**
- Inteligência Artificial / Fabric
- Campeonato Mundial de Power BI / visualização de dados
- Carreira e comunidade

### Próximos eventos (mencionados na live)
- **21 de julho** — Sessão com Alison Pezzott e Sidney Cirqueira sobre comunidades e engajamento
- **21 de julho (2h depois)** — Sessão com Paulo Grijó e Gustavo (campeões mundiais de Power BI)

---

## 🎟️ Como conseguir o voucher gratuito (100% de desconto)

Para retirar o voucher da DP-600, DP-700 ou DP-800:

1. Participar da comunidade do Data Days (pelo menos 2 dias de sessões — live ou sob demanda)
2. Concluir pelo menos **3 módulos do Microsoft Learn**
3. Submeter o formulário de requisição até **10 de agosto de 2026**
4. Aguardar 1–2 semanas para receber o código

> ⚠️ Sem o voucher, o exame custa cerca de **US$165** (~R$600). Com voucher, é praticamente gratuito — mas se reprovar, normalmente é necessário pagar para refazer.

**Links oficiais:**
- [Formulário de requisição do voucher (válido até 10/08/2026)](https://community.fabric.microsoft.com/t5/custom/page/page-id/campaign_form?campaignID=Y2FtcGFpZ24tMTc4MTEwNTMxMDAxMQ==)
- [Página oficial dos eventos Data Days em português — Microsoft Reactor](https://developer.microsoft.com/en-us/reactor/series/S-1682/?wt.mc_id=datadayslive_S-1682_social_reactor)

---

## 📝 Sobre o exame DP-700

| Item | Detalhe |
|---|---|
| Nível | Intermediário |
| Duração | ~100 minutos |
| Idiomas | Inglês (recomendado) e Português disponível |
| Nota de corte | A partir de 700 (recomendado buscar bem acima disso) |
| Próxima atualização do exame | **21 de julho** |
| Público-alvo | Analytics Engineers, Data Engineers, Arquitetos, Analistas e Administradores que desenham e implantam soluções de engenharia de dados/analytics no Fabric |

🔗 Página oficial da certificação: [Microsoft Certified: Fabric Data Engineer Associate](https://learn.microsoft.com/en-us/credentials/certifications/fabric-data-engineer-associate/?practice-assessment-type=certification)

🔗 Study Guide oficial: [Study Guide for Exam DP-700](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/dp-700)

### Pré-requisitos de conhecimento
- **SQL** — considerado padrão obrigatório para engenheiros de dados
- **KQL (Kusto Query Language)** — muito similar à lógica do SQL; importante para Real-Time Intelligence
- **PySpark** — ponto muito importante para a prova

### Estrutura da prova
- **2** estudos de caso (cenários reais/fictícios) no início
- **3** perguntas com resposta única em sequência, com pequenas variações entre elas (atenção: errar uma pode indicar erro nas demais)
- Perguntas de **múltipla escolha**
- Perguntas de **organização** (ordenar passos/etapas)
- Perguntas de **complemento de código** (completar trechos de código)

### Pesos das áreas de conhecimento da prova (30-35% cada)
1. Implementação e gerenciamento de soluções de analytics
2. Ingestão e transformação de dados
3. Monitoramento e otimização de um ambiente analítico

> ⚠️ Atenção: o conteúdo cobrado inclui não só funcionalidades em **General Availability (GA)**, mas também funcionalidades em **Preview** que já são de uso comum (ex: Workspace Identity, OneLake Security, Source Control para Data Warehouse).

---

## 📚 Skills Measured — Tópicos detalhados

### 1. Implementação e gerenciamento de uma solução de analytics
- Configuração de workspace (Spark, domínios, Lakehouse)
- Configuração de **Workspace Identity** no Fabric (saiu recentemente do preview)
- CI/CD no Microsoft Fabric (Database Projects para Data Warehouse/Lakehouse)
- Deployment Pipelines
  - 📖 [Fabricators guide to Microsoft Fabric deployment pipelines — Kevin Chant](https://www.kevinrchant.com/2024/11/06/fabricators-guide-to-microsoft-fabric-deployment-pipelines/)
- **Segurança e governança**:
  - Permissões de workspace e de item
    - 📖 [Understand the Fabric security model](https://learn.microsoft.com/en-us/training/modules/secure-data-access-in-fabric/2-understand-fabric-security-model)
  - Permissões granulares: **Row Level Security (RLS)**, **Column Level Security (CLS)**, **Object Level Security**, **Dynamic Data Masking (DDM)**, Granular SQL Permissions
    - 📖 [Secure a Microsoft Fabric data warehouse — Training](https://learn.microsoft.com/en-us/training/modules/secure-data-warehouse-in-microsoft-fabric/?wt.mc_id=certsustainedmkt_portfolioupdate_blog_wwl&source=docs&ns-enrollment-type=Collection&ns-enrollment-id=p34pu1ex4y4r2z)
    - ▶️ [Playlist: Segurança no Microsoft Fabric](https://youtube.com/playlist?list=PLNZqHhJp9syUoKVaNm_M-dwlW0IBvLbDl&si=6Kyzzq5-u4NjDxwb)
  - **OneLake Security** (granularização de acesso por pastas, como no ADLS Gen2)
  - Lakehouse e Sensitivity Labels
  - Endorsement de itens no Fabric (Promoted / Certified)
    - 📖 [Govern data in Fabric — Training](https://learn.microsoft.com/en-us/training/modules/administer-fabric/5-govern-fabric)
    - **Promoted**: membros do workspace com papel de Contributor ou Admin podem promover conteúdo dentro do workspace; o admin do Fabric pode promover conteúdo em toda a organização
    - **Certified**: exige processo formal de revisão por um revisor designado; conteúdo aparece com badge "Certified" no portal; admins gerenciam e podem customizar esse processo
  - Auditoria de logs no Microsoft Fabric

### 2. Ingestão e transformação de dados
- Escolha entre **Dataflow Gen2**, **Pipeline** e **Notebook**
- Triggers **data-driven** e **event-driven**
  - 📖 [Data pipelines storage event triggers in Data Factory](https://learn.microsoft.com/en-us/fabric/data-factory/pipeline-storage-event-triggers)
- Parametrização de pipelines e notebooks (dynamic functions/expressões dinâmicas do Data Factory)
- Padrões de carga: **full load** vs **incremental load** (best practices)
- Preparação de ambiente / carga para modelo dimensional
- Ingestão e transformação via **Dataflow, Notebooks, KQL, SQL**
- Qual ferramenta apropriada para cada cenário de processamento de dados
- Features para melhorar performance do consumo de dados
- Uso e gerenciamento de **Shortcuts**
  - 📖 [Unify data sources with OneLake shortcuts — caching](https://learn.microsoft.com/en-us/fabric/onelake/onelake-shortcuts#caching)
  - ⚠️ Importante: arquivos **maiores que 1 GB não entram no cache do Shortcut**; existe tempo de cache e quantidade de dados configuráveis
- Transformações com **PySpark, SQL, KQL** (denormalização, agrupamento, criação de tabelas com KQL)
- **Real-Time Analytics / Streaming**:
  - Funções de **janelamento (windowing)** — conceito de streaming aplicável em qualquer plataforma (Fabric, Databricks, Synapse, Stream Analytics, etc.)
    - 📖 [Windowing - Stream Analytics Query](https://learn.microsoft.com/en-us/stream-analytics-query/windowing-azure-stream-analytics)
    - **Tumbling windows**: dividem os eventos recebidos em intervalos fixos e não sobrepostos, baseados no horário de chegada
  - Azure Event Hubs, CDC, tipos de transformações
  - Entender código KQL e Event Processor Operators
  - Roteamento de streams via Real-Time Analytics
    - 📖 [Routing event stream data — Training](https://learn.microsoft.com/en-us/training/modules/explore-event-streams-microsoft-fabric/4-route-event-data-to-destinations)

### 3. Monitoramento e otimização
- Monitoramento de pipelines e dataflows; configuração de alertas
- Refresh de modelo semântico
- Identificação e resolução de erros (performance, falhas de carga)
- **Spark — parametrização e execução de DAGs**
  - 📖 [Microsoft Spark Utilities (MSSparkUtils) — run multiple notebooks with parameters](https://learn.microsoft.com/en-us/fabric/data-engineering/microsoft-spark-utilities)
- **Isolamento — High Concurrency Mode** (otimização de custo e performance de jobs)
  - 📖 [High concurrency mode in Apache Spark compute for Fabric](https://learn.microsoft.com/en-us/fabric/data-engineering/high-concurrency-overview)
- **Manutenção do Delta Lake**: `OPTIMIZE`, `V-Order` (quando habilitar/desabilitar), `VACUUM`, merge no Delta Lake
  - 📖 [Delta table maintenance in Microsoft Fabric](https://learn.microsoft.com/en-us/fabric/data-engineering/lakehouse-table-maintenance)
  - ▶️ [Lakehouse no Microsoft Fabric: Optimize, V-Order e Vacuum na Prática](https://www.youtube.com/watch?v=LpjiGL4Im30)
- Otimização de leitura/escrita no OneLake
- **Integração com Git**:
  - Conectividade com GitHub e Azure DevOps
  - Organização + Projeto + Repositório Git + Branch + Git Folder
  - Configurações administrativas de integração com Git
  - Permissões: 📖 [Git integration process — Permissions](https://learn.microsoft.com/en-us/fabric/cicd/git-integration/git-integration-process?tabs=Azure%2Cazure-devops#permissions)
  - 📺 Recomendado: vídeos do **Alison Pezzott** sobre Git/GitHub no Fabric — [Canal Alison Pezzott](https://www.youtube.com/@alisonpezzott)
- **Source Control para objetos do Data Warehouse** (ainda em preview, mas cai na prova)
  - 📖 [Source control with Warehouse (preview)](https://learn.microsoft.com/en-us/fabric/data-warehouse/source-control)
  - Tipos de dados e Database Objects no Data Warehouse
- Quando usar determinadas atividades no Data Factory

### 🏗️ Arquitetura Medalhão (Bronze / Silver / Gold)
- 📖 [Optimizing Spark Compute for Medallion Architectures in Microsoft Fabric](https://blog.fabric.microsoft.com/en-US/blog/optimizing-spark-compute-for-medallion-architectures-in-microsoft-fabric/)
- Melhor maneira de carregar dados para a camada **Bronze**
- Melhor maneira de processar dados na camada **Silver**

---

## 🧭 Estratégia de estudo recomendada

1. **Não decore — aprenda de verdade.** O objetivo não é só passar, é estar preparado para entrevistas técnicas reais.
2. Siga o **Microsoft Learn (DP-700 Learning Path)** — ~30h de conteúdo
   - 1h/dia → completa em ~1 mês
   - 2h/dia → completa em ~15 dias
3. Complete os **exercícios práticos** (hands-on, via [mslearn-fabric](https://microsoftlearning.github.io/mslearn-fabric/)) vinculados a cada módulo do Learn — não só a teoria
4. Leia a **documentação oficial** da Microsoft — várias perguntas da prova vêm diretamente de lá, não apenas do Learn
5. Use o **Assessment oficial** (50 perguntas) apenas como validação de conhecimento, não como guia principal de estudo
6. Pratique no ambiente real do Fabric (capacidade trial) — documente o aprendizado (ex: posts no LinkedIn)
7. Estude conteúdos complementares: arquitetura medalhão, comparação Pipeline vs Notebook, vídeos da comunidade

---

## 🔗 Recursos e Links

### Documentação e treinamento oficial Microsoft Learn
- [Microsoft Certified: Fabric Data Engineer Associate — Página da certificação](https://learn.microsoft.com/en-us/credentials/certifications/fabric-data-engineer-associate/?practice-assessment-type=certification)
- [Study Guide for Exam DP-700](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/dp-700)
- [mslearn-fabric — Exercícios práticos (hands-on)](https://microsoftlearning.github.io/mslearn-fabric/)
- [Secure a Microsoft Fabric data warehouse — Training](https://learn.microsoft.com/en-us/training/modules/secure-data-warehouse-in-microsoft-fabric/?wt.mc_id=certsustainedmkt_portfolioupdate_blog_wwl&source=docs&ns-enrollment-type=Collection&ns-enrollment-id=p34pu1ex4y4r2z)
- [Understand the Fabric security model](https://learn.microsoft.com/en-us/training/modules/secure-data-access-in-fabric/2-understand-fabric-security-model)
- [Govern data in Fabric — Training](https://learn.microsoft.com/en-us/training/modules/administer-fabric/5-govern-fabric)
- [Unify data sources with OneLake shortcuts (caching)](https://learn.microsoft.com/en-us/fabric/onelake/onelake-shortcuts#caching)
- [Delta table maintenance in Microsoft Fabric](https://learn.microsoft.com/en-us/fabric/data-engineering/lakehouse-table-maintenance)
- [Windowing - Stream Analytics Query](https://learn.microsoft.com/en-us/stream-analytics-query/windowing-azure-stream-analytics)
- [Routing event stream data — Training](https://learn.microsoft.com/en-us/training/modules/explore-event-streams-microsoft-fabric/4-route-event-data-to-destinations)
- [Microsoft Spark Utilities (MSSparkUtils) for Fabric](https://learn.microsoft.com/en-us/fabric/data-engineering/microsoft-spark-utilities)
- [High concurrency mode in Apache Spark compute for Fabric](https://learn.microsoft.com/en-us/fabric/data-engineering/high-concurrency-overview)
- [Data pipelines storage event triggers in Data Factory](https://learn.microsoft.com/en-us/fabric/data-factory/pipeline-storage-event-triggers)
- [Git integration process (Permissions)](https://learn.microsoft.com/en-us/fabric/cicd/git-integration/git-integration-process?tabs=Azure%2Cazure-devops#permissions)
- [Source control with Warehouse (preview)](https://learn.microsoft.com/en-us/fabric/data-warehouse/source-control)

### Blogs e materiais da comunidade
- [Optimizing Spark Compute for Medallion Architectures — Microsoft Fabric Blog](https://blog.fabric.microsoft.com/en-US/blog/optimizing-spark-compute-for-medallion-architectures-in-microsoft-fabric/)
- [DP-700 Skills Measured Resources — Andy Cutler (serverlesssql.com)](https://www.serverlesssql.com/dp-700-microsoft-fabric-data-engineering-associate-skills-measured-resources/)
- [Fabricators guide to Microsoft Fabric deployment pipelines — Kevin Chant](https://www.kevinrchant.com/2024/11/06/fabricators-guide-to-microsoft-fabric-deployment-pipelines/)

### Vídeos e canais (YouTube)
- ▶️ [Canal Sidney Cirqueira — Dominando o Microsoft Fabric](https://www.youtube.com/@SidneyCirqueira)
- ▶️ [Canal Alison Pezzott](https://www.youtube.com/@alisonpezzott)
- ▶️ [Playlist: Segurança no Microsoft Fabric](https://youtube.com/playlist?list=PLNZqHhJp9syUoKVaNm_M-dwlW0IBvLbDl&si=6Kyzzq5-u4NjDxwb)
- ▶️ [Lakehouse no Microsoft Fabric: Optimize, V-Order e Vacuum na Prática](https://www.youtube.com/watch?v=LpjiGL4Im30)
- ▶️ [DP-700 Exam Prep Course (11 vídeos) — Will](https://www.youtube.com/watch?v=XECqSfKmtCk&list=PLug2zSFKZmV2Ue5udYFeKnyf1Jj0-y5Gy)
- ▶️ [DP-700 Exam Full Course — Aleksi](https://www.youtube.com/watch?v=jTDSP7KBavI)

### Formulários e cadastro (Data Days)
- [Formulário de requisição do voucher (válido até 10/08/2026)](https://community.fabric.microsoft.com/t5/custom/page/page-id/campaign_form?campaignID=Y2FtcGFpZ24tMTc4MTEwNTMxMDAxMQ==)
- [Página oficial de eventos Data Days (PT-BR) — Microsoft Reactor](https://developer.microsoft.com/en-us/reactor/series/S-1682/?wt.mc_id=datadayslive_S-1682_social_reactor)

---

## 💬 Notas finais da live

- A prova será atualizada em **21 de julho** — revisar o Study Guide após essa data
- DP-700 é considerada mais tranquila que a antiga **DP-203** (descontinuada)
- IA pode ajudar na execução, mas não substitui o entendimento técnico necessário para orientar a IA corretamente
- Recomendado fazer a prova em **inglês** (evita problemas de tradução de termos técnicos)

---

*Documento gerado a partir da transcrição da live do Data Days (Sidney Cirqueira), com links de estudo complementares organizados por tópico.*
