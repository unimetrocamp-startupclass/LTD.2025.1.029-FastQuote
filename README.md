# LTD.2025.1.029-FastQuote
Sistema de cotação automatizado para empresas: gera PDFs e envia por E-mail.

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

---

## Dados do Cliente

Título do Projeto: FastQuote – Solução rápida em cotações via WebSite

Cliente: AguiaFix – A Solução Em Fixadores

CNPJ/CPF: 06.886.538/0001-21

Contato: Vinicius Mastrangelo Dias

Email do contato: Vendas2@aguiafix.com.br

---

## Equipe de Desenvolvimento

| Nome completo              | Curso                                 | Disciplina                              |
|----------------------------|---------------------------------------|-----------------------------------------|
| Vinicius Mastrangelo Dias  | Análise e Desenvolvimento de Sistemas | Programação Orientada a Objetos em java |
| João Lucas Las Casas Alves | Análise e Desenvolvimento de Sistemas | Programação Orientada a Objetos em java |

**Professor Orientador:** Kesede Rodrigues Julio

---

## 1. Introdução

A área de vendas da AguiaFix enfrenta desafios no processo de recebimento e processamento de cotações enviadas por clientes online. Atualmente, os clientes enviam suas listas de itens via WhatsApp, exigindo uma longa troca de mensagens para coleta de dados. Isso torna o processo lento e propenso a falhas. 
O projeto FastQuote resolve esse problema oferecendo um formulário estruturado no site da AguiaFix, permitindo que o cliente insira as informações de forma clara, rápida e precisa. Este sistema utiliza tecnologias modernas para automatizar a geração da cotação, verificar estoque em uma planilha Excel e gerar um PDF que será enviado automaticamente para o setor de vendas.

---

## 2. Objetivo

Automatizar o processo de cotação de produtos da AguiaFix para que os clientes possam preencher um formulário diretamente no site, sem depender de troca de mensagens com o vendedor.
Isso reduz o tempo de resposta, organiza os dados recebidos e melhora a taxa de conversão de cotações em vendas.

---

## 3. Escopo

**Escopo incluído:**
- Formulário dividido em etapas: Empresa, Cotação, Itens e Revisão
- Campos validados com JavaScript, máscaras e escolhas guiadas
- Geração de PDF no backend com os dados da cotação
- Verificação dos itens com base na planilha de estoque
- Armazenamento da cotação no banco de dados
- Envio via E-mail

**Escopo fora:**
- Dashboard para histórico no frontend (por enquanto)
- Integração com ERP
- Envio automatico por WhatsApp

---

## 4. Backlogs do Produto

| ID  | Título (Resumo)                       | Descrição                                                                                    | Status       | Prioridade | Entrega |
|-----|---------------------------------------|----------------------------------------------------------------------------------------------|--------------|------------|---------|
| A01 | Escolha do Projeto                    | Definição do tema e nome do projeto junto ao cliente                                         | Concluído    | Alta       | 20/03   |
| A02 | Planejamento Inicial                  | Organização das etapas do projeto e primeiras ideias no Jira                                 | Concluído    | Alta       | 20/03   |
| A03 | Primeira Reunião com Cliente          | Levantamento de requisitos e entendimento do problema                                        | Concluído    | Alta       | 20/03   |
| PFQU-26 | Estrutura inicial e organização do repositório | Estrutura da documentação, cadastro do time, modelagem inicial e repositório GitHub/Jira     | Concluído    | Alta       | 20/03   |
| B01 | Estrutura do Formulário Multietapas   | Criar formulário dividido em 4 etapas com barra de progresso                                 | Concluído    | Alta       | 10/04   |
| B02 | Validação de campos obrigatórios      | Impedir avanço entre etapas caso campos estejam vazios ou inválidos                          | Concluído    | Alta       | 10/04   |
| B05 | Feedback visual em campos inválidos   | Mostrar borda vermelha e mensagens nos campos obrigatórios                                   | Concluído    | Alta       | 10/04   |
| B03 | Máscara para CNPJ e Telefone          | Aplicar máscara automática nos campos CNPJ e telefone                                        | Concluído    | Média      | 10/04   |
| B04 | Dropdown com itens da planilha        | Adicionar campo de seleção de itens com base na planilha de estoque                          | Concluído    | Alta       | 10/04   |
| B09 | Campo de Comentários                  | Adicionar campo de texto livre para observações na aba de Itens                              | Concluído    | Média      | 10/04   |
| B06 | Barra de Progresso                    | Indicar etapa atual do formulário com barra visual                                           | Concluído    | Média      | 10/04   |
| B07 | Feedback de envio com sucesso         | Mostrar alerta animado e resetar o formulário após envio                                     | Concluído    | Média      | 10/04   |
| B08 | Responsividade para Mobile            | Adaptar o formulário para diferentes tamanhos de tela                                        | Concluído    | Alta       | 10/04   |
| B10 | Ajustes visuais e melhorias gerais    | Alinhamentos, espaçamentos, melhorias visuais e foco em UX                                   | Concluído    | Média      | 17/04   |
| C01 | Endpoint de Recebimento do Formulário | Backend REST que recebe e valida os dados da cotação                                         | Concluído    | Alta       | 17/04   |
| C02 | Leitura da Planilha estoque.xlsx      | Verifica itens e quantidades disponíveis para resposta dinâmica                              | Concluído    | Alta       | 17/04   |
| C03 | Geração de PDF com status de itens    | PDF detalhado gerado no backend com dados da cotação e análise de estoque                    | Concluído    | Alta       | 17/04   |
| C04 | Salvar Cotação no Banco de Dados      | Salvar cotação com vínculo entre cliente e itens no MySQL usando JPA                         | Concluído    | Alta       | 17/04   |
| C05 | Armazenamento de PDF no Disco         | PDF salvo automaticamente em /cotacoes/ com ID da cotação                                    | Concluído    | Média      | 17/04   |
| C06 | Histórico de Cotações                 | Registro com data/hora e dados para controle de cotações                                     | Concluído    | Média      | 24/04   |
| C07 | Exibição do Histórico                 | Endpoint GET para visualizar histórico no painel do sistema                                  | Concluído    | Média      | 24/04   |
| C08 | Envio do PDF por E-mail               | PDF gerado será enviado automaticamente ao cliente por e-mail com link para download         | Concluído    | Alta       | 15/05   |
| C10 | Dashboard para Vendedores (Admin)     | Painel administrativo com lista, filtros e controle de cotações                              | Concluído    | Baixa      | 05/06   |
| D01 | Semana da Tecnologia                  | Apresentação intermediária do sistema                                                        | Concluído    | Média      | 15/05   |
| D02 | FENETEC – Feira de Negócios           | Apresentação final do projeto com banner e funcionalidade rodando                            | Em andamento | Alta       | 05/06   |

---

## 5. Cronograma

| Entrega      | Data      | Descrição                                                              |
|--------------|-----------|------------------------------------------------------------------------|
| Entrega 1    | 20/03/2025| Escolha do projeto, planejamento inicial, primeira reunião com cliente |
| Entrega 2    | 10/04/2025| Entrega de todos os itens do frontend                                  |
| Entrega 3    | 17/04/2025| Primeira parte do backend (endpoints, leitura da planilha, PDF, banco) |
| Entrega 4    | 24/04/2025| Continuação do backend (histórico, exibição)                           |
| SemanaTec    | 15/05/2025| Apresentação intermediária do sistema                                  |
| FENETEC      | 05/06/2025| Apresentação final com o sistema completo funcionando                  |

---

## 6. Materiais e Métodos

## Modelagem do Sistema

Para representar a estrutura e o comportamento do sistema FastQuote, utilizamos dois tipos de diagramas UML:

### 1. Diagrama de Caso de Uso

Representa os principais atores do sistema (cliente e vendedor) e suas interações com os processos do sistema.

![diagrama_caso_de_uso_sem_emoji](https://github.com/user-attachments/assets/ffd4ef4e-9620-400b-9368-ff5552ac76a0)

### 2. Modelo Entidade-Relacionamento (MER)

Mostra a estrutura de dados e os relacionamentos entre as entidades do banco de dados (cotação, itens e histórico).

![diagrama_mer](https://github.com/user-attachments/assets/cfa6899e-5b04-4030-a4cb-138e29c43d48)

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

## Arquitetura do Sistema

O sistema FastQuote foi desenvolvido com uma arquitetura dividida entre frontend e backend, com integração de planilha de estoque, geração de PDF e envio automatizado via WhatsApp. O fluxo de dados segue as etapas descritas no diagrama abaixo:

![arquitetura_sistema_email](https://github.com/user-attachments/assets/998a1401-0227-4d0a-abff-0a50d504a68d)

---

## 7. Resultados

A implantação do sistema FastQuote trouxe melhorias significativas para a empresa AguiaFix:

- Redução de mais de 60% no tempo médio de resposta das cotações.
- Aumento da clareza nas informações recebidas dos clientes.
- Automatização do processo de geração de cotações em PDF.
- Melhoria na organização e rastreabilidade de pedidos recebidos.
- Estímulo à adoção digital por parte dos vendedores.

Além disso, os testes internos demonstraram a eficácia do sistema, validando a estrutura do formulário, o cruzamento com o estoque e a entrega via PDF.

---

## 8. Conclusão

Com o desenvolvimento do FastQuote, foi possível observar uma transformação positiva no processo de recebimento de cotações da empresa AguiaFix. A solução proposta atendeu aos requisitos do cliente, modernizou a comunicação e trouxe agilidade ao setor de vendas.
A integração entre frontend e backend garantiu robustez na geração de PDFs e verificação de estoque, mostrando que tecnologias web podem ser aliadas poderosas mesmo em negócios tradicionais.

O projeto também contribuiu significativamente para o aprendizado prático, integrando conceitos de programação orientada a objetos, banco de dados, consumo de APIs e boas práticas de UX/UI.

### Melhorias Futuras:
Para versões futuras do sistema, está prevista a implementação de um painel administrativo com login para vendedores, onde será possível visualizar o histórico completo das cotações, aplicar filtros e acessar estatísticas de conversão. Além disso, pretende-se integrar o sistema com o ERP da empresa e expandir os canais de envio da cotação, permitindo que o PDF também seja enviado automaticamente por WhatsApp, além do e-mail já implementado.

---

## 9. Homologação do MVP junto ao cliente

Após as entregas parciais, realizadas de acordo com os requisitos do sistema e cronograma, o MVP foi apresentado em uma reunião, realizada entre o time de desenvolvedores e o cliente.

<h4>Fotos da Homologação:</h4>

<div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: center;">

  <div>
    <img src="https://github.com/user-attachments/assets/4200b820-81dd-4927-8628-c9d7385a8874" width="475"/>
    <p><strong>Foto 1:</strong> Da esquerda para a direita: Vinicius Mastrangelo Dias (em pé) e Andre da Silva Franco (sentado) </p>
  </div>

  <div>
    <img src="https://github.com/user-attachments/assets/46a2e138-380d-4d21-949c-5a7af2c65b67" width="475"/>
    <p><strong>Foto 2:</strong> Apresentador: Vinicius Mastrangelo Dias</p>
  </div>

  <div>
    <img src="https://github.com/user-attachments/assets/4da8693d-77ee-4ab1-b98d-eaa60922c2af" width="475"/>
    <p><strong>Foto 3:</strong> Participantes da homologação assistindo à apresentação</p>
  </div>

<div>
  <img src="https://github.com/user-attachments/assets/82143322-66ed-445c-a659-5a7bdea8e201" width="475"/>
  <p><strong>Foto 4:</strong> Plano geral do local da reunião</p>
</div>

</div>

<h4>Lista de Presença</h4>

Segue abaixo a lista de presentes na homologação do MVP.

<img src="https://github.com/user-attachments/assets/d87996a1-2027-4bbf-b984-a23d42a2abbc" width="475"/>

<p>Ao final da apresentação, o sistema foi homologado pelo cliente.</p>

---

Ao final da apresentação, o sistema foi homologado pelo cliente.
---

## 10. Divulgação

#### Publicações no LinkedIn
Artigo de João Lucas Las Casas Alves:
https://www.linkedin.com/pulse/fastquote-apresenta%C3%A7%C3%A3o-parcial-jo%C3%A3o-lucas-las-casas-alves-qu8wf/

Artigo de Vinicius Mastrangelo Dias:
https://www.linkedin.com/pulse/fastquote-apresenta%C3%A7%C3%A3o-parcial-vinicius-mastrangelo-juasf/?trackingId=31NK68hFwHdIUs1vKZiUZQ%3D%3D

#### Perfis Pessoais:

João Lucas Las Casas Alves: https://www.linkedin.com/in/joaolucas-dev

Vinicius Mastrangelo Dias: https://www.linkedin.com/in/vinicius-mastrangelo-177976250

### Prints das Publicações
Perfil de João Lucas Las Casas Alves
<img src="https://github.com/user-attachments/assets/689cb325-291a-4578-ac5c-8ed73234de06" width="600"/>
Artigo de João Lucas
<img src="https://github.com/user-attachments/assets/60b482ac-c8c5-49c3-8816-0c8940b4aa1e" width="600"/>
Artigo de Vinicius Mastrangelo Dias
<img src="https://github.com/user-attachments/assets/77202e24-f524-417d-bf42-ddd4c9d2bd8e" width="600"/>
Perfil de Vinicius
<img src="https://github.com/user-attachments/assets/3fe2cc71-a51c-4730-a918-6fcc013dbca6" width="600"/>
Semana da Tecnologia
O projeto FastQuote foi apresentado oficialmente durante a Semana da Tecnologia, em um seminário com a presença de colegas, professores e avaliadores. Abaixo estão os registros fotográficos da apresentação:

Foto 1 – João e Vinicius apresentando o projeto
<img src="https://github.com/user-attachments/assets/3d928a1b-f788-4882-8fb8-d68e6b97049d" width="600"/>
Foto 2 – Participantes assistindo à apresentação
<img src="https://github.com/user-attachments/assets/438fbf04-a1b6-4350-b78c-62610ad438d8" width="600"/>
Foto 3 – Projeção do slide inicial com o logo do LTD
<img src="https://github.com/user-attachments/assets/743e5ddb-2b33-40eb-939d-efed01f0388b" width="600"/>
Foto 4 – Foto geral com todos reunidos ao final da apresentação
<img src="https://github.com/user-attachments/assets/d7e46913-9226-474d-80f4-2677331e2e7f" width="600"/>

### FENETEC: Feira de Negócios em Tecnologia:

Imagens da apresentação:
(Indisponiveis ainda)

Lista de presença:
(Indisponivel ainda)

---

## 11. Carta de Apresentação

<img src="https://github.com/user-attachments/assets/4a7503d7-7a71-480d-aa82-26ff4ade30bc" width="600"/>
<img src="https://github.com/user-attachments/assets/4484a93c-6306-4336-beda-6d42ef83963f" width="600"/>

📄 [Baixar Carta de Apresentação (.odt)](https://github.com/user-attachments/files/20301510/Carta.de.Apresentacao.1.odt)

---

## 12. Carta de Autorização

<img src="https://github.com/user-attachments/assets/1ee61fbb-b5b8-40c3-8803-f83732b52977" width="600"/>

📄 [Baixar Carta de Autorização (.pdf)](https://github.com/user-attachments/files/20301516/CARTA.DE.AUTORIZACAO.pdf)

---

## 13. Relato individual do processo

### João Lucas Las Casas Alves

Durante o desenvolvimento do projeto FastQuote, tive a oportunidade de atuar diretamente na parte de backend do sistema. Foquei na criação dos endpoints em Java usando Spring Boot, bem como na manipulação dos dados da planilha de estoque utilizando Apache POI. Também fui responsável pela geração de PDFs dinâmicos com base nas informações preenchidas no formulário, utilizando a biblioteca OpenPDF.

Esse trabalho me permitiu aprofundar meus conhecimentos em persistência de dados com JPA/Hibernate e em boas práticas de estruturação de API. Trabalhei para garantir que o sistema fosse funcional, escalável e integrado com as necessidades do cliente. Aprendi muito sobre como transformar requisitos práticos em lógica de sistema, especialmente nas etapas que envolviam validação e organização das cotações.

### Vinicius Mastrangelo Dias

Durante o projeto FastQuote, atuei principalmente no desenvolvimento do frontend e na interface com o cliente. Fui responsável por implementar o formulário de múltiplas etapas, aplicar validações, máscaras e garantir a responsividade utilizando TailwindCSS, Choices.js e Flatpickr. Além disso, cuidei do visual e da experiência do usuário ao longo do processo de cotação.

No aspecto de negócio, tive um papel fundamental na comunicação com o cliente AguiaFix. Participei das reuniões de levantamento de requisitos, entendi a dor do processo manual de cotações e ajudei a traduzir essas necessidades em soluções visuais e práticas. Essa experiência me fez evoluir não só tecnicamente, mas também na forma de lidar com necessidades reais e apresentar entregas de valor.





