# LTD.2025.1.029-FastQuote
Sistema de cotação automatizado para empresas: gera PDFs e envia por WhatsApp.

# Documentação do Sistema

## SUMÁRIO
* [Dados do Cliente](#dados-do-cliente)
* [Equipe de Desenvolvimento](#equipe-de-desenvolvimento)
1. [Introdução](#1-introdução)
2. [Objetivo](#2-objetivo)
3. [Escopo](#3-escopo)
4. [Backlogs do Produto](#4-backlogs-do-produto)
5. [Cronograma](#5-cronograma)
6. [Materiais e Métodos](#6-materiais-e-métodos)
7. [Resultados](#7-resultados)
8. [Conclusão](#8-conclusão)
9. [Homologação do MVP junto ao cliente](#9-homologação-do-mvp-junto-ao-cliente)
10. [Divulgação](#10-divulgação)
11. [Carta de Apresentação](#11-carta-de-apresentação)
12. [Carta de Autorização](#12-carta-de-autorização)
13. [Relato individual do processo](#13-relato-individual-do-processo)

## Dados do Cliente

Título do Projeto: FastQuote – Solução rápida em cotações via WebSite

Cliente: AguiaFix – A Solução Em Fixadores

CNPJ/CPF: 06.886.538/0001-21

Contato: Vinicius Mastrangelo Dias

Email do contato: Vendas2@aguiafix.com.br

## Equipe de Desenvolvimento

| Nome completo              | Curso                                 | Disciplina                              |
|----------------------------|---------------------------------------|-----------------------------------------|
| Vinicius Mastrangelo Dias  | Análise e Desenvolvimento de Sistemas | Programação Orientada a Objetos em java |
| João Lucas Las Casas Alves | Análise e Desenvolvimento de Sistemas | Programação Orientada a Objetos em java |

**Professor Orientador:** Kesede Rodrigues Julio

## 1. Introdução

A área de vendas da AguiaFix enfrenta desafios no processo de recebimento e processamento de cotações enviadas por clientes online. Atualmente, os clientes enviam suas listas de itens via WhatsApp, exigindo uma longa troca de mensagens para coleta de dados. Isso torna o processo lento e propenso a falhas. 
O projeto FastQuote resolve esse problema oferecendo um formulário estruturado no site da AguiaFix, permitindo que o cliente insira as informações de forma clara, rápida e precisa. Este sistema utiliza tecnologias modernas para automatizar a geração da cotação, verificar estoque em uma planilha Excel e gerar um PDF que será enviado automaticamente para o setor de vendas.

## 2. Objetivo

Automatizar o processo de cotação de produtos da AguiaFix para que os clientes possam preencher um formulário diretamente no site, sem depender de troca de mensagens com o vendedor.
Isso reduz o tempo de resposta, organiza os dados recebidos e melhora a taxa de conversão de cotações em vendas.

## 3. Escopo

**Escopo incluído:**
- Formulário dividido em etapas: Empresa, Cotação, Itens e Revisão
- Campos validados com JavaScript, máscaras e escolhas guiadas
- Geração de PDF no backend com os dados da cotação
- Verificação dos itens com base na planilha de estoque
- Armazenamento da cotação no banco de dados
- Envio futuro via WhatsApp utilizando a API do 360dialog

**Escopo fora:**
- Dashboard para histórico no frontend (por enquanto)
- Login de administrador
- Integração com ERP

## 4. Backlogs do Produto

| ID  | Título (Resumo)                       | Descrição                                                                                    | Status       | Prioridade | Entrega |
|-----|---------------------------------------|----------------------------------------------------------------------------------------------|--------------|------------|---------|
| A01 | Escolha do Projeto                    | Definição do tema e nome do projeto junto ao cliente                                         | Concluído    | Alta       | 20/03   |
| A02 | Planejamento Inicial                  | Organização das etapas do projeto e primeiras ideias no Jira                                 | Concluído    | Alta       | 20/03   |
| A03 | Primeira Reunião com Cliente          | Levantamento de requisitos e entendimento do problema                                        | Concluído    | Alta       | 20/03   |
| B01 | Estrutura do Formulário Multietapas   | Criar formulário dividido em 4 etapas com barra de progresso                                 | Concluído    | Alta       | 10/04   |
| B02 | Validação de campos obrigatórios      | Impedir avanço entre etapas caso campos estejam vazios ou inválidos                          | Concluído    | Alta       | 10/04   |
| B03 | Máscara para CNPJ e Telefone          | Aplicar máscara automática nos campos CNPJ e telefone                                        | Concluído    | Média      | 10/04   |
| B04 | Dropdown com itens da planilha        | Adicionar campo de seleção de itens com base na planilha de estoque                          | Concluído    | Alta       | 10/04   |
| B05 | Feedback visual em campos inválidos   | Mostrar borda vermelha e mensagens nos campos obrigatórios                                   | Concluído    | Alta       | 10/04   |
| B06 | Barra de Progresso                    | Indicar etapa atual do formulário com barra visual                                           | Concluído    | Média      | 10/04   |
| B07 | Feedback de envio com sucesso         | Mostrar alerta animado e resetar o formulário após envio                                     | Concluído    | Média      | 10/04   |
| B08 | Responsividade para Mobile            | Adaptar o formulário para diferentes tamanhos de tela                                        | Concluído    | Alta       | 10/04   |
| B09 | Campo de Comentários                  | Adicionar campo de texto livre para observações na aba de Itens                              | Concluído    | Média      | 10/04   |
| B10 | Ajustes visuais e melhorias gerais    | Alinhamentos, espaçamentos, melhorias visuais e foco em UX                                   | Em andamento | Média      | 17/04   |
| C01 | Endpoint de Recebimento do Formulário | Backend REST que recebe e valida os dados da cotação                                         | Em andamento | Alta       | 17/04   |
| C02 | Leitura da Planilha estoque.xlsx      | Verifica itens e quantidades disponíveis para resposta dinâmica                              | Em andamento | Alta       | 17/04   |
| C03 | Geração de PDF com status de itens    | PDF detalhado gerado no backend com dados da cotação e análise de estoque                    | Em andamento | Alta       | 17/04   |
| C04 | Salvar Cotação no Banco de Dados      | Salvar cotação com vínculo entre cliente e itens no MySQL usando JPA                         | Em andamento | Alta       | 17/04   |
| C05 | Armazenamento de PDF no Disco         | PDF salvo automaticamente em /cotacoes/ com ID da cotação                                    | Em andamento | Média      | 17/04   |
| C06 | Histórico de Cotações                 | Registro com data/hora e dados para controle de cotações                                     | Em andamento | Média      | 24/04   |
| C07 | Exibição do Histórico                 | Endpoint GET para visualizar histórico no painel do sistema                                  | Em andamento | Média      | 24/04   |
| C08 | Envio do PDF via WhatsApp             | PDF enviado automaticamente ao grupo de vendedores usando API 360dialog                      | Planejado    | Alta       | 15/05   |
| C09 | Envio por E-mail ou Link ao Cliente   | PDF poderá ser enviado também para o cliente por e-mail ou link                              | Planejado    | Média      | 15/05   |
| C10 | Dashboard para Vendedores (Admin)     | Painel administrativo com lista, filtros e controle de cotações                              | Planejado    | Baixa      | 05/06   |
| D01 | Semana da Tecnologia                  | Evento de apresentação intermediária para testes e feedbacks                                 | Planejado    | Média      | 15/05   |
| D02 | FENETEC – Feira de Negócios           | Apresentação final do projeto com banner e funcionalidade rodando                            | Planejado    | Alta       | 05/06   |

## 5. Cronograma

| Entrega      | Data      | Descrição                                                              |
|--------------|-----------|------------------------------------------------------------------------|
| Entrega 1    | 20/03/2025| Escolha do projeto, planejamento inicial, primeira reunião com cliente |
| Entrega 2    | 10/04/2025| Entrega de todos os itens do frontend                                  |
| Entrega 3    | 17/04/2025| Primeira parte do backend (endpoints, leitura da planilha, PDF, banco) |
| Entrega 4    | 24/04/2025| Continuação do backend (histórico, exibição)                           |
| SemanaTec    | 15/05/2025| Apresentação intermediária do sistema                                  |
| FENETEC      | 05/06/2025| Apresentação final com o sistema completo funcionando                  |

## 6. Materiais e Métodos

### Modelagem do Sistema

- Diagrama de Entidade Relacionamento (MER): elaborado com base nas entidades `Cotacao`, `Item`, `Historico` e seus relacionamentos;
- Diagrama de Casos de Uso: descrevendo o fluxo de interação entre cliente e sistema;

### Tecnologias Utilizadas

**Frontend**
- HTML, CSS, JavaScript
- TailwindCSS – Estilização responsiva e moderna
- Choices.js – Dropdown estilizado e com busca
- Flatpickr – Seleção de datas estilizada

**Backend**
- Java
- Spring Boot – Estrutura principal do backend
- Apache POI – Leitura da planilha Excel com estoque
- OpenPDF – Geração do PDF da cotação
- MySQL – Armazenamento das cotações e histórico
- JPA / Hibernate – Persistência de dados

**Ferramentas de Apoio**
- WebStorm – Frontend
- IntelliJ IDEA – Backend
- Jira – Organização de tarefas e cronograma

## 7. Resultados

**Conteúdo a ser preenchido após homologação e testes finais.**

## 8. Conclusão

**Conteúdo a ser preenchido após finalização de todas as entregas.**

## 9. Homologação do MVP junto ao cliente

**Será preenchido após validação oficial com o cliente.**

## 10. Divulgação

**Conteúdo será preenchido com links e prints das redes sociais, LinkedIn e vídeo.**

## 11. Carta de Apresentação

**Será gerada e assinada conforme orientações do professor.**

## 12. Carta de Autorização

**Será preenchida e assinada pelo cliente após reunião de alinhamento.**

## 13. Relato individual do processo

**Espaço reservado para cada integrante inserir seu relato pessoal após finalização do projeto.**





