<div align="center">

  <img src="https://www.catolicasc.org.br/wp-content/themes/catolicasc_v1/assets/dist/images/lp/logo_csc_footer.png" alt="Logo Católica SC" width="150" style="margin-bottom: 20px;" />

  <h1>ENGENHARIA DE SOFTWARE</h1>
  
  <h2>Católica SC</h2>
  
  <h3>Proposta Técnica de Projeto de Portfólio</h3>
  
  <h4>Plataforma de Cobrança Automatizada com Processamento de Dados e Gestão de Régua de Comunicação</h4>

  <br>

  <table style="margin-left: auto; margin-right: auto; text-align: left;">
    <tr>
      <th>Linha de Projeto</th>
      <td>Web / Dados / Automação</td>
    </tr>
    <tr>
      <th>Autor</th>
      <td>Mariele Vieira da Silva</td>
    </tr>
    <tr>
      <th>Data da Proposta</th>
      <td>12/04/2026</td>
    </tr>
    <tr>
      <th>Versão</th>
      <td>1.0</td>
    </tr>
  </table>

</div> 

---

## Sumário
* [1. Visão do Produto e Impacto](#1-visão-do-produto-e-impacto)
  * [1.1 Contexto e Problema](#11-contexto-e-problema)
  * [1.2 Origem da Demanda e Evidências](#12-origem-da-demanda-e-evidências)
  * [1.3 Análise de Soluções Existentes (Benchmark)](#13-análise-de-soluções-existentes-benchmark)
  * [1.4 Público-Alvo](#14-público-alvo)
  * [1.5 Objetivos do Projeto](#15-objetivos-do-projeto)
  * [1.6 Métricas de Sucesso (KPIs)](#16-métricas-de-sucesso-kpis)
* [2. Engenharia de Requisitos](#2-engenharia-de-requisitos)
  * [2.1 Personas](#21-personas)
  * [2.2 Casos de Uso Principais](#22-casos-de-uso-principais)
  * [2.3 Requisitos Funcionais](#23-requisitos-funcionais)
  * [2.4 Requisitos Não Funcionais](#24-requisitos-não-funcionais)
  * [2.5 Regras de Negócio](#25-regras-de-negócio)
  * [2.6 Fora do Escopo](#26-fora-do-escopo)
* [3. Fluxos e Comportamento do Sistema](#3-fluxos-e-comportamento-do-sistema)
  * [3.1 Fluxo Principal — Ingestão e Validação de Lotes](#31-fluxo-principal--ingestão-e-validação-de-lotes)
  * [3.2 Fluxo Secundário — Execução da Régua de Cobrança](#32-fluxo-secundário--execução-da-régua-de-cobrança)
  * [3.3 Fluxos Alternativos e Exceções](#33-fluxos-alternativos-e-exceções)
* [4. Mockups e Experiência do Usuário (UX)](#4-mockups-e-experiência-do-usuário-ux)
  * [4.1 Fluxo de Navegação](#41-fluxo-de-navegação)
  * [4.2 Descrição das Telas Principais](#42-descrição-das-telas-principais)
  * [4.3 Fluxo de Interação — Importação de Lote](#43-fluxo-de-interação--importação-de-lote)
* [5. Arquitetura do Sistema](#5-arquitetura-do-sistema)
  * [5.1 Diagrama C4](#51-diagrama-c4)
  * [5.2 Modelo de Dados](#52-modelo-de-dados)
  * [5.3 Stack Tecnológica](#53-stack-tecnológica)
* [6. Segurança e Privacidade](#6-segurança-e-privacidade)
  * [6.1 Controles de Segurança](#61-controles-de-segurança)
  * [6.2 Privacidade e LGPD](#62-privacidade-e-lgpd)
* [7. Planejamento do Projeto](#7-planejamento-do-projeto)
* [8. Referências](#8-referências)
* [9. Apêndices](#9-apêndices)
* [10. Parecer do Comitê de Avaliação](#10-parecer-do-comitê-de-avaliação)

---

## 1. Visão do Produto e Impacto

### 1.1 Contexto e Problema
A inadimplência é um desafio estrutural para empresas de diversos segmentos no Brasil. Segundo dados do Serasa Experian, o país ultrapassa 70 milhões de pessoas físicas inadimplentes, e empresas de médio porte perdem, em média, entre 3% e 8% da sua receita bruta anual em decorrência de cobranças mal executadas ou não realizadas. O processo tradicional de cobrança é majoritariamente manual: analistas financeiros exportam planilhas do ERP( Enterprise Resource Planning - software de gestão que integra todos os departamentos de produção), filtram manualmente os devedores, enviam e-mails individualmente e registram os contatos em outros sistemas. 

Esse fluxo apresenta limitações críticas:
* Alto custo operacional com tarefas repetitivas e de baixo valor.
* Inconsistência na régua de comunicação; cada analista aplica regras diferentes.
* Ausência de rastreabilidade e auditoria das ações realizadas.
* Impossibilidade de escalar o volume de cobranças sem aumentar o quadro de funcionários.
* Dados de retorno (pagamentos, negociações) não realimentam o sistema de forma automatizada.

Este projeto propõe substituir esse fluxo por uma plataforma web integrada que automatiza a ingestão de dados de inadimplentes, aplica regras de cobrança configuráveis e executa disparos de comunicação multicanal (e-mail, SMS, WhatsApp) de forma programada e monitorada.

### 1.2 Origem da Demanda e Evidências
**Pesquisa com Usuários**
Foram realizadas entrevistas exploratórias com os profissionais da área financeira e de cobrança da empresa parceira. As principais dores identificadas foram:
* 100% dos entrevistados relatam que o processo de envio de comunicações de cobrança é realizado manualmente.
* Mais de 80% afirmam não possuir rastreabilidade sobre quais devedores receberam qual tipo de comunicação.
* Todos mencionaram a dificuldade de manter uma régua de cobrança padronizada entre diferentes analistas.
* A empresa não utiliza uma solução dedicada integrada, usam combinações de planilhas no excel, e-mail corporativo e sistemas legados.

### 1.3 Análise de Soluções Existentes (Benchmark)
Foram analisadas as principais soluções disponíveis no mercado que se propõem a resolver problemas semelhantes:

| Solução | Público-Alvo | Pontos Fortes | Limitações |
| :--- | :--- | :--- | :--- |
| Receita Certa | PMEs | Interface amigável, integração com Pix | Sem customização de régua, sem importação por CSV |
| Assertiva Cobranças | Empresas de médio porte | Automação básica de comunicação | Custo elevado, sem observabilidade |
| Iugu / Vindi | E-commerce e SaaS | Plataforma de pagamentos robusta | Foco em recorrência, não em cobranças de carteira |
| Planilha + Disparador de e-mail | Qualquer empresa | Baixo custo, familiar | Sem automação, sem rastreabilidade, sem escala |


**Diferencial do Projeto**
Nenhuma das soluções analisadas oferece simultaneamente: (1) importação flexível de lotes via CSV/Excel com validação automatizada; (2) configuration visual da régua de cobrança por perfil de devedor; (3) execução de jobs programados com monitoramento em tempo real via dashboard. O projeto preenche essa lacuna com uma arquitetura moderna, open source e auditável.

### 1.4 Público-Alvo
O sistema é direcionado a empresas de médio porte, como cooperativas, varejistas, clínicas e prestadoras de serviço, que realizam a gestão interna de suas carteiras de inadimplentes. O usuário primário é o analista financeiro ou de cobrança, que possui nível intermediário de conhecimento tecnológico e utiliza a aplicação via navegador web. O perfil secundário engloba o gestor financeiro, responsável por acessar os dashboards de monitoramento e configurar os parâmetros estratégicos da régua de cobrança. Este projeto é desenvolvido em parceria com a Consulth Soluções Empresariais (CNPJ 33.536.315/0001-07), é uma empresa especializada em recuperação de crédito e cobrança B2B ( Business-to-Business ). Ela atua auxiliando outras empresas a negociarem e resgatarem valores de títulos em atraso, buscando acordos justos e sustentáveis entre credor e cliente.

### 1.5 Objetivos do Projeto
**Objetivo Geral**
Desenvolver uma plataforma web para automação do ciclo de cobrança de inadimplentes, desde a ingestão e validação de dados até o disparo multicanal de comunicações e o monitoramento dos resultados, com arquitetura orientada a qualidade, segurança e observabilidade.

**Objetivos Específicos**
* Implementar um pipeline assíncrono de ingestão e validação de arquivos CSV/Excel com feedback detalhado de erros por linha
* Desenvolver um módulo de configuração visual da régua de cobrança, permitindo definir canais e prazos por perfil de devedor
* Automatizar a execução de jobs de disparo de comunicações (e-mail e SMS) com agendamento configurável
* Criar um dashboard de monitoramento com métricas de execução, taxa de entrega e taxa de conversão
* Garantir qualidade de código com TDD, CI/CD automatizado e análise estática via SonarCloud

### 1.6 Métricas de Sucesso (KPIs)

| KPI | Meta |
| :--- | :--- |
| Tempo de resposta da API (P95) | < 300ms |
| Throughput de processamento de lote | > 10.000 registros/minuto |
| Cobertura de testes automatizados (backend) | >= 80% |
| Cobertura de testes (frontend) | >= 25% |
| Disponibilidade do serviço | >= 99% |
| Taxa de sucesso nos disparos de e-mail | > 95% |
| Qualidade Sonar Cloud (Quality Gate) | Aprovado (sem blockers/criticals) |


---

## 2. Engenharia de Requisitos

### 2.1 Personas

| Persona 1: Heloizi Vargas | Analista de Cobrança | Contexto: Trabalha em uma cooperativa de crédito e cobrança. Gerencia uma carteira de 2.000 devedores por mês. | Objetivo: Enviar comunicações de cobrança sem precisar fazer isso manualmente uma a uma. | Dores: Perde horas exportando planilhas do ERP e enviando e-mails individualmente. Comete erros ao filtrar devedores por prazo, o que gera cobrança indevida podendo causar processos à cooperativa. |
| :--- | :--- | :--- | :--- | :--- |
| Persona 2: Fellipe Junkes | Gestor Financeiro | Contexto: Responsável pela estratégia de recuperação de crédito em cobrança B2B. | Objetivo: Visualizar em tempo real o desempenho das campanhas de cobrança e ajustar a régua conforme o perfil dos devedores. | Dores: Não tem visibilidade sobre quais ações foram tomadas. Não consegue mensurar o retorno das comunicações enviadas. |


### 2.2 Casos de Uso Principais

* **UC01:** Importar lote de devedores via arquivo CSV/Excel
* **UC02:** Visualizar relatório de validação do lote importado
* **UC03:** Configurar régua de cobrança (canal, prazo, mensagem)
* **UC04:** Visualizar lista de devedores e seus status de comunicação
* **UC05:** Monitorar execução dos jobs de disparo em tempo real
* **UC06:** Consultar histórico de comunicações enviadas por devedor
* **UC07:** Gerenciar usuários e permissões de acesso

**Perfis e Acessos:**
* **Analista de Cobrança** - responsável pelos fluxos operacionais do dia a dia: importar lotes (UC01), visualizar o relatório de validação (UC02, que inclui o UC01), consultar a lista de devedores (UC04) e o histórico de comunicações por devedor (UC06).
* **Gestor Financeiro** - acesso estratégico e de configuração: configurar a régua de cobrança (UC03), monitorar os jobs em tempo real (UC05), visualizar o dashboard de acordos fechados (UC06, que inclui UC05), e acesso estendido à lista de devedores (UC04 compartilhado).
* **Administrador** - gestão do sistema: gerenciar usuários (UC03), com sub-fluxos de criar/editar usuário (UC05) e definir perfil de acesso (UC04).

**Detalhamento da UC07**
O diagrama mostra o UC07 com dois escopos bem delimitados:
* **Gestor Financeiro** pode criar/editar usuários com perfil Operador, redefinir senhas, ativar/desativar contas e visualizar a lista de usuários. A nota de restrição deixa explícito que ele não pode criar ou promover Gestores nem Administradores.
* **Administrador** tem acesso total: gerencia qualquer perfil, define e altera níveis de acesso, exclui usuários e ainda acessa o log de auditoria, funcionalidade exclusiva desse perfil.

### 2.3 Requisitos Funcionais
* **RF01:** O sistema deve permitir que o usuário realize upload de arquivos CSV e Excel (.xlsx) com dados de devedores.
* **RF02:** O sistema deve processar o arquivo de forma assíncrona e exibir o progresso em tempo real.
* **RF03:** O sistema deve validar cada linha do arquivo importado conforme regras de negócio configuradas e exibir relatório detalhado de erros por linha.
* **RF04:** O sistema deve permitir que o usuário configure a régua de cobrança, definindo canais (e-mail, SMS, WhatsApp), prazo de atraso e template de mensagem.
* **RF05:** O sistema deve permitir que o usuário visualize a lista de devedores com filtros por status, prazo e canal.
* **RF06:** O sistema deve executar jobs programados para disparar comunicações aos devedores elegíveis conforme a régua configurada.
* **RF07:** O sistema deve registrar o resultado de cada tentativa de disparo (sucesso, falha, bounce).
* **RF08:** O sistema deve exibir um dashboard com métricas de execução: total de disparos, taxa de entrega e taxa de conversão.
* **RF09:** O sistema deve permitir autenticação de usuários com controle de perfis (operador, gestor, administrador).
* **RF10:** O sistema deve permitir que o administrador gerencie usuários e permissões.

### 2.4 Requisitos Não Funcionais
* **RNF01:** O sistema deve suportar ao menos 100 usuários simultâneos sem degradação de desempenho.
* **RNF02:** O tempo de resposta das rotas de API deve ser inferior a 300 ms no percentil 95 (P95).
* **RNF03:** O pipeline de processamento de lotes deve suportar arquivos de até 50.000 registros.
* **RNF04:** O sistema deve utilizar autenticação JWT com tokens de curta duração e refresh token.
* **RNF05:** Todos os dados sensíveis devem ser armazenados com criptografia em repouso.
* **RNF06:** O sistema deve atingir cobertura mínima de 80% nos testes automatizados do backend (pytest).
* **RNF07:** O pipeline CI/CD deve impedir o deploy caso os testes falhem ou o Quality Gate do Sonar Cloud não seja aprovado.
* **RNF08:** O sistema deve expor métricas no formato Prometheus para coleta e visualização no Grafana.
* **RNF09:** Todos os serviços devem ser conteinerizados com Docker e orquestrados via Docker Compose.

### 2.5 Regras de Negócio
* **RN01:** Somente usuários autenticados com perfil de 'operador' ou superior podem realizar importações de lotes.
* **RN02:** A régua de cobrança só pode ser ativada após ao menos uma regra válida ser configurada.
* **RN03:** Um devedor não pode receber mais de uma comunicação do mesmo canal no mesmo dia.
* **RN04:** Linhas com CPF/CNPJ inválido são rejeitadas na validação e não ingressam na base de devedores.
* **RN05:** Jobs de disparo são executados apenas em dias úteis, entre 08h00 e 20h00 (horário de Brasília).
* **RN06:** Somente administradores podem criar, editar ou remover usuários do sistema.

### 2.6 Fora do Escopo
* Integração direta com sistemas de pagamento ou emissão de boletos
* Portal de autoatendimento para o devedor final
* Módulo de negociação ou parcelamento de dívidas
* Importação por integração via API com ERPs externos
* Suporte a canais de voz (ligações telefônicas automatizadas)
* Aplicativo mobile

---

## 3. Fluxos e Comportamento do Sistema

### 3.1 Fluxo Principal — Ingestão e Validação de Lotes
O fluxo de ingestão é o ponto de entrada de dados no sistema. Abaixo estão as etapas do fluxo principal:

| Etapa | Ator | Descrição |
| :--- | :--- | :--- |
| 1 | Usuário | Acesse o portal web e selecione a opção de importar lote |
| 2 | Usuário | Realiza upload do arquivo CSV ou Excel (.xlsx) |
| 3 | Backend (API) | Recebe o arquivo, valida o formato e publica mensagem na fila RabbitMQ/Kafka |
| 4 | Worker Python | Consome a mensagem da fila, le o arquivo linha a linha usando pandas |
| 5 | Worker Python | Aplica validações: CPF/CNPJ, campos obrigatórios, formatos de data e valor |
| 6 | Worker Python | Persiste registros válidos no PostgreSQL e registra erros em tabela de log |
| 7 | Backend (API) | Atualiza o status do job de importação no banco de dados |
| 8 | Frontend | Exibe relatório com totais: importados com sucesso, rejeitados e erros por linha |


### 3.2 Fluxo Secundário — Execução da Régua de Cobrança
Os jobs de disparo são executados de forma programada. O fluxo a seguir descreve a execução automática:
* O scheduler (Celery Beat ou Scheduler) aciona o job no horário configurado
* O worker consulta a base de devedores elegíveis conforme as regras da régua ativa
* Para cada devedor elegível, o worker chama a API de disparo (e-mail via SendGrid, SMS via Twilio)
* O resultado de cada chamada (sucesso, falha, bounce) é registrado na tabela de comunicações
* O dashboard é atualizado com as métricas consolidadas

### 3.3 Fluxos Alternativos e Exceções
* **Arquivo inválido:** caso o arquivo enviado não seja CSV nem XLSX, o sistema retorna erro HTTP 422 imediatamente, sem enfileirar.
* **Fila indisponível:** se o broker de mensagens estiver fora do ar, a API retorna erro 503 com mensagem orientativa ao usuário.
* **Falha no disparo externo:** erros na API de e-mail/SMS são registrados com código de erro e tentativa de reenvio após 30 minutos (máximo 3 tentativas).
* **Usuário não autenticado:** qualquer rota protegida retorna HTTP 401 e redireciona para o login.

---

## 4. Mockups e Experiência do Usuário (UX)

### 4.1 Fluxo de Navegação
O fluxo de navegação do sistema funciona por meio de rolagem de tela, segue a estrutura abaixo:
* Login → Dashboard → Importar Lote → Relatório de Validação
* Dashboard → Régua de Cobrança → Configurar Regra → Lista de Devedores
* Dashboard → Monitoramento → Detalhe do Job → Histórico do Devedor

### 4.2 Descrição das Telas Principais
Link de acesso ao projeto no Figma: <https://www.figma.com/design/aTgE91sZyzbxTrB8kh5cIh/Plataforma-de-Cobran%C3%A7a-Automatizada?node-id=0-1&t=vxq6D656IlNc1dOZ-1>

* **Tela 1 — Login:** Tela de Login – Plataforma de Cobrança. Formulário de autenticação com campos de e-mail e senha. Inclui feedback de erro para credenciais inválidas e link de recuperação de senha. Autenticação via JWT.
* **Tela 2 — Dashboard Principal:** Tela de Dachboard – Plataforma de Cobrança. Exibe KPIs consolidados: total de devedores na base, disparos realizados no dia, taxa de entrega e alertas de falhas. Inclui gráfico de timeline de disparos e acesso rápido às funcionalidades principais.
* **Tela 3 — Importar Lote:** Tela de Importação de Lote – Plataforma de Cobrança. Interface de upload com drag-and-drop. Exibe o progresso do processamento assíncrono em tempo real (barra de progresso e log de status). Após conclusão, redireciona para o relatório de validação.
* **Tela 4 — Relatório de Validação:** Tela de Relatório de Validação – Plataforma de Cobrança. Tabela detalhando o resultado da importação: total de registros, aprovados e rejeitados. Listagem das linhas com erro, identificando o campo problemático e a regra violada. Permite download do relatório de erros em CSV.
* **Tela 5 — Régua de Cobrança:** Tela de Régua de Cobrança – Plataforma de Cobrança. Interface de configuração das regras de disparo. O usuário define para cada perfil (ex: atraso de 5, 15 e 30 dias): canal de comunicação, template de mensagem e horário preferencial. Inclui preview do template antes de salvar.
* **Tela 6 — Monitoramento de Jobs:** Tela de Monitoramento – Plataforma de Cobrança. Dashboard em tempo real exibindo: jobs em execução, concluídos e com falha. Métricas de disparos por canal, taxa de sucesso e gráfico histórico. Permite acesso ao log detalhado de cada execução.

### 4.3 Fluxo de Interação — Importação de Lote
1. O usuário acessa a tela 'Importar Lote' pelo Menu.
2. Arrasta o arquivo CSV para a área de upload ou clica para selecionar.
3. O sistema exibe a barra de progresso enquanto o arquivo é enviado à API.
4. A API enfileira o processamento e retorna o ID do job.
5. O frontend consulta periodicamente o status do job (polling ou WebSocket).
6. Ao concluir, o sistema redireciona automaticamente para o relatório de validação.
7. O usuário revisa os erros, corrige o arquivo original e pode importar se necessário.

---

## 5. Arquitetura do Sistema

### 5.1 Diagrama C4
**Nível 1 — Diagrama de Contexto**
O sistema interage com os seguintes atores e sistemas externos:

| Elemento | Tipo | Descrição |
| :--- | :--- | :--- |
| Analista de Cobrança | Usuário | Realiza importações de lotes e monitora o status dos disparos via portal web |
| Gestor Financeiro | Usuário | Configura a régua de cobrança e analisa métricas no dashboard |
| Administrador | Usuário | Gerência usuários, permissões e configurações globais do sistema |
| SendGrid / AWS SES | Sistema Externo | API de disparo de e-mails transacionais |
| Twilio / AWS SNS | Sistema Externo | API de disparo de SMS |
| Prometheus + Grafana | Sistema Externo | Coleta e visualização de métricas de observabilidade |
| SonarCloud | Sistema Externo | Análise estática de código e quality gate no pipeline CI/CD |
| GitHub Actions | Sistema Externo | Orquestração do pipeline de CI/CD |


**Nível 2 — Diagrama de Containers**
O sistema é composto pelos seguintes contêineres, cada um executando em seu próprio container Docker:

| Container | Tecnologia | Responsabilidade |
| :--- | :--- | :--- |
| Frontend (SPA) | React + Vite | Interface web para interação do usuário. Consome a REST API. |
| API Gateway / Backend | Python (Fast API) | Expõe as rotas REST, gerência autenticação JWT e publica mensagens na fila. |
| Worker de Processamento | Python (Celery/Worker) | Consome mensagens da fila, processa arquivos com pandas e persiste os dados. |
| Broker de Mensagens | RabbitMQ | Desacopla o upload do arquivo do processamento. Garante a durabilidade das mensagens. |
| Banco de Dados Principal | PostgreSQL 15 | Persistência de devedores, regras de cobrança, jobs e logs de comunicação. |
| Cache e Session Store | Redis | Cache de sessões JWT e resultados temporários de jobs. |
| Observabilidade | Prometheus + Grafana | Coleta de métricas de sistema e visualização em dashboards. |


**Nível 3 — Diagrama de Componentes (Backend Fast API)**
Internamente, a API segue uma arquitetura em camadas:

| Camada | Componentes | Responsabilidade |
| :--- | :--- | :--- |
| Controllers (Routers) | BatchRouter, RulesRouter, JobsRouter, AuthRouter | Recebem e validam as requisições HTTP. Delegam para a camada de serviços. |
| Services | BatchService, NotificationService, AuthService, JobService | Contém a lógica de negócio. Orquestram repositórios e clientes externos. |
| Repositories | BatchRepository, DebtorRepository, CommunicationRepository | Abstraem o acesso ao banco de dados via SQLAlchemy ORM. |
| Clients | EmailClient, SMSClient, BrokerClient | Encapsulam a comunicação com APIs externas (SendGrid, Twilio, RabbitMQ). |
| Models / Schemas | Pydantic Models, SQLAlchemy Models | Definem os contratos de dados para validação e persistência. |


### 5.2 Modelo de Dados
O banco de dados PostgreSQL é organizado nas seguintes entidades principais:

| Entidade | Principais Campos | Relacionamentos |
| :--- | :--- | :--- |
| users | id, email, password_hash, role, created_at | Criador de batches e regras |
| batches | id, user_id, filename, status, total_rows, valid_rows, error_rows, created_at | Pertence a users; tem muitos debtors e batch_errors |
| batch_errors | id, batch_id, row_number, field, error_message | Pertence a batches |
| debtors | id, batch_id, cpf_cnpj, name, email, phone, amount_due, due_date, status | Pertence a batches; tem muitas communications |
| collection_rules | id, user_id, days_overdue, channel, template_id, active | Define a régua de cobrança |
| jobs | id, rule_id, started_at, finished_at, status, dispatched, success, failed | Pertence a collection_rules; tem muitas communications |
| communications | id, debtor_id, job_id, channel, sent_at, status, error_code | Registra cada tentativa de disparo |


### 5.3 Stack Tecnológica

| Tecnologia | Uso | Justificativa |
| :--- | :--- | :--- |
| Python 3.11 + Fast API | Backend e Workers | Alta produtividade para APIs REST, tipagem com Pydantic, suporte nativo a async/await e ecossistema rico para data processing. |
| React 18 + Vite | Frontend (SPA) | Biblioteca madura para SPAs, grande ecossistema, build performática e suporte a PWA para futuras evoluções. |
| PostgreSQL 15 | Banco de Dados Relacional | Robusto para modelagem transacional, suporte a JSON para dados flexíveis, ACID-compliante. |
| RabbitMQ | Message Broker | Filas duráveis para desacoplar a ingestão do processamento; protocolo AMQP amplamente suportado. |
| Redis | Cache e Session Store | Cache in-memory de alta performance para sessões e resultados temporários de jobs. |
| Celery + Celery Beat | Task Queue e Scheduler | Framework Python para execução assíncrona de tasks e agendamento de jobs recorrentes. |
| Docker + Docker Compose | Conteinerização | Garante ambiente reproduzível em dev, CI e produção. Facilita o deploy na VPS. |
| GitHub Actions | CI/CD | Integração nativa com GitHub, gratuito para repositórios públicos, ampla biblioteca de actions. |
| Pytest | Testes de Backend | Framework de testes padrao do ecossistema Python; suporte a fixtures, mocks e cobertura. |
| Jest + Testing Library | Testes de Frontend | Padrão para testes de componentes React; integrado ao ecossistema Vite. |
| SonarCloud | Análise Estática | Quality gate automatizado no CI/CD; detecta code smells, vulnerabilidades e dívida técnica. |
| Prometheus + Grafana | Observabilidade | Stack open source de referência para métricas e dashboards; integração com Fast API via starlette-exporter. |


---

## 6. Segurança e Privacidade
A plataforma lida com dados financeiros e pessoais de devedores, o que exige atenção rigorosa à segurança em todas as camadas.

### 6.1 Controles de Segurança
* Autenticação via JWT (access token de 15 minutos + refresh token de 7 dias, armazenado em cookie httpOnly).
* Autorização baseada em perfis (RBAC): operador, gestor e administrador com permissões distintas.
* Proteção contra OWASP Top 10: validação de inputs com Pydantic, prevenção de SQL Injection via ORM parametrizado, headers de segurança (HSTS, CSP, X-Frame-Options).
* Rate limiting nas rotas de autenticação para mitigar ataques de força bruta.
* Comunicação HTTPS obrigatória em produção (TLS via Nginx reverse proxy).
* Senhas armazenadas com hash bcrypt (custo 12).
* Variáveis de ambiente e secrets gerenciados fora do repositório (GitHub Secrets / arquivo .env não versionado).
* Análise de vulnerabilidades no pipeline CI/CD via Sonar Cloud e dependa bot.

### 6.2 Privacidade e LGPD
O sistema coleta e processa dados pessoais de devedores (CPF/CNPJ, nome, e-mail, telefone e informações financeiras). Seguem as medidas de conformidade com a LGPD (Lei 13.709/2018):
* Os dados são coletados exclusivamente das empresas parceiras (controladoras), que são responsáveis pela base legal de tratamento.
* Dados sensíveis (valor da dívida, histórico de comunicações) são armazenados em colunas com criptografia em nível de aplicação.
* Logs de acesso e auditoria são mantidos por 90 dias e anonimizados após esse período.
* A API disponibiliza endpoint para exclusão de todos os dados de um devedor (right to erasure — Art. 18, LGPD).
* Não há compartilhamento de dados com terceiros além das APIs de disparo (SendGrid/Twilio), com acordos de processamento de dados em vigor.

---

## 7. Planejamento do Projeto

| Marco | Descrição | Prazo Estimado |
| :--- | :--- | :--- |
| M1: Setup e Fundação | Configuração do repositório, Docker Compose com todos os serviços, estrutura base do Fast API e React, pipeline CI/CD inicial com GitHub Actions e SonarCloud. | Semana 1-2 |
| M2: Fluxo 1: Ingestão e Validação | Implementação do upload de arquivos, integração com RabbitMQ, worker de processamento com pandas, validações de negócio e relatório de erros. TDD: testes unitários para todas as regras de validação. | Semana 3-5 |
| M3: Fluxo 2: Régua de Cobrança | CRUD de regras de cobrança, interface de configuração no frontend, modelo de dados de devedores e status. Testes de integração para as rotas da API. | Semana 6-7 |
| M4: Fluxo 3: Jobs e Monitoramento | Implementação do scheduler (Celery Beat), integração com APIs de e-mail e SMS, dashboard de monitoramento e métricas Prometheus. | Semana 8-10. |
| M5: Qualidade e Observabilidade | Alcance das metas de cobertura de testes (80% backend, 25% frontend), ajustes de Quality Gate no Sonar Cloud, configuração dos dashboards Grafana. | Semana 11-12 |
| M6: Deploy e Documentação | Deploy em VPS com Docker, configuração de HTTPS, documentação final (OpenAPI/Swagger, README, RFC), apresentação. | Semana 13-14 |


---

## 8. Referências
* FastAPI Documentation — https://fastapi.tiangolo.com
* Celery Documentation — https://docs.celeryq.dev
* RabbitMQ Official Docs — https://www.rabbitmq.com/documentation.html
* Prometheus Python Client — https://github.com/prometheus/client_python
* SonarCloud Documentation — https://docs.sonarcloud.io
* OWASP Top 10 (2021) — https://owasp.org/www-project-top-ten
* LGPD — Lei nº 13.709/2018 — http://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm
* CRISP-DM Reference Model — Chapman et al. (2000)
* C4 Model — Simon Brown — https://c4model.com
* GitHub Actions Documentation — https://docs.github.com/actions
* Docker Documentation — https://docs.docker.com
* PostgreSQL 15 Documentation — https://www.postgresql.org/docs/15/

---

## 9. Apêndices
Os seguintes artefatos complementares devem ser incluídos neste documento após a fase de design:
* **Apêndice A** — Wireframes detalhados de todas as telas (Figma ou Excalidraw)
* **Apêndice B** — Diagrama Entidade-Relacionamento (DER) completo do banco de dados
* **Apêndice C** — Diagrama de sequência UML dos fluxos de ingestão e disparo
* **Apêndice D** — Exemplos de arquivos CSV aceitos e relatório de validação gerado
* **Apêndice E** — Configuração do pipeline GitHub Actions (arquivo .yml comentado)
* **Apêndice F** — Exemplos de métricas do Prometheus e painéis do Grafana
* **Apêndice G** — Transcrições das entrevistas com usuários realizadas na fase de descoberta

---

## 10. Parecer do Comitê de Avaliação
(A ser preenchido pelos professores avaliadores)

| Avaliador 1: __________________________________________ | |
| :--- | :--- |
| Status: [ ] Aprovado [ ] Ajustar | |
| Observações: | |
| ____________________________________________________________________________________ | |
| ____________________________________________________________________________________ | |
| **Avaliador 2: __________________________________________** | |
| Status: [ ] Aprovado [ ] Ajustar | |
| Observações: | |
| ____________________________________________________________________________________ | |
| ____________________________________________________________________________________ | |
| **Avaliador 3: __________________________________________** | |
| Status: [ ] Aprovado [ ] Ajustar | |
| Observações: | |
| ____________________________________________________________________________________ | |
| ____________________________________________________________________________________ | |
