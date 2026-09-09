# 💧 Sistema Embarcado para Monitoramento Inteligente de Caixas d'Água e Cisternas

> **Sistema embarcado baseado em ESP32 para monitoramento inteligente de caixas d'água e cisternas, com previsão de falta de água e geração de dashboards de consumo.**

---

## 👥 Integrantes

| Integrante           |
| -------------------- |
| **Marcos Belo**      |
| **Jefferson Amorim** |
| **Tácito Juno**      |

---

## 📋 Descrição do Projeto

Este projeto consiste no desenvolvimento de um **sistema embarcado baseado em ESP32** destinado ao monitoramento inteligente de caixas d'água e cisternas.

A proposta é utilizar dados coletados do sistema de armazenamento de água para acompanhar seu comportamento ao longo do tempo, permitindo identificar situações de baixo nível, acompanhar o consumo e auxiliar na **previsão de possíveis períodos de falta de água**.

Além da aquisição e processamento dos dados, o projeto contempla a disponibilização das informações por meio de **dashboards**, permitindo uma visualização mais clara do consumo e das condições do reservatório.

### 🎯 Objetivos

* Monitorar o nível de água em caixas d'água e cisternas;
* Realizar a aquisição e processamento dos dados;
* Identificar situações de nível crítico;
* Auxiliar na previsão de falta de água;
* Registrar informações relacionadas ao consumo;
* Disponibilizar os dados de forma visual por meio de dashboards;
* Desenvolver uma solução integrada utilizando ESP32.

---

## ⚠️ Problema

A falta de acompanhamento contínuo do nível de água em caixas d'água e cisternas pode dificultar a identificação antecipada de situações de baixo abastecimento.

Em sistemas convencionais, muitas vezes o acompanhamento depende de verificações manuais, tornando mais difícil perceber padrões de consumo, alterações no nível do reservatório e possíveis situações de falta de água com antecedência.

Diante desse cenário, o projeto busca desenvolver uma solução capaz de **automatizar o monitoramento**, organizar os dados coletados e transformá-los em informações úteis para acompanhamento e tomada de decisão.

---

## 💡 Solução Proposta

A solução proposta é composta por um sistema embarcado responsável pela coleta das informações do reservatório, processamento dos dados e disponibilização dessas informações para visualização.

De maneira geral, o funcionamento pode ser representado pelo seguinte fluxo:

```text
┌─────────────────────┐
│      Reservatório   │
│  Caixa d'água /     │
│      Cisterna       │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│      Sensores       │
│  Aquisição de dados │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│        ESP32        │
│ Processamento dos   │
│      dados          │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│ Comunicação /       │
│ armazenamento       │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│     Dashboard       │
│                     │
│ Nível • Consumo •   │
│ Histórico • Alertas │
└─────────────────────┘
```

---

## 🏗️ Arquitetura do Sistema

A arquitetura do sistema é organizada em diferentes camadas, permitindo separar as responsabilidades de aquisição, processamento, comunicação e visualização dos dados.

### Camada de aquisição

Responsável pela obtenção das informações relacionadas ao estado do reservatório.

### Camada embarcada

O **ESP32** atua como unidade central do sistema embarcado, sendo responsável pelo processamento das informações provenientes da aquisição.

### Camada de comunicação

Responsável pelo envio das informações coletadas pelo sistema embarcado para as demais partes da aplicação.

### Camada de dados

Responsável pelo armazenamento e organização das informações coletadas, permitindo análises históricas e acompanhamento do comportamento do consumo.

### Camada de visualização

Responsável pela apresentação das informações por meio de dashboards, facilitando a interpretação dos dados.

---

## 🔧 Hardware

O projeto utiliza o **ESP32 como plataforma principal do sistema embarcado**.

### Componentes

| Componente             | Função                                    | Status                |
| ---------------------- | ----------------------------------------- | --------------------- |
| ESP32                  | Unidade de processamento e controle       | 🔄 Em desenvolvimento |
| Sensores               | Aquisição das informações do reservatório | 🔄 Em desenvolvimento |
| Reservatório           | Ambiente monitorado                       | 🔄 Em desenvolvimento |
| Componentes auxiliares | Integração e funcionamento do circuito    | 🔄 Em desenvolvimento |

> A lista de componentes poderá ser atualizada conforme a definição final do hardware.

---

## 💻 Software

A parte de software será responsável por integrar a coleta, o processamento, a comunicação e a apresentação dos dados.

### Componentes previstos

```text
Firmware
   │
   ├── Aquisição de dados
   ├── Processamento
   ├── Regras de monitoramento
   └── Comunicação
          │
          ▼
       Sistema
          │
          ├── Armazenamento
          └── Dashboard
```

### Funcionalidades

* Leitura dos dados dos sensores;
* Processamento das informações;
* Monitoramento do nível do reservatório;
* Identificação de condições críticas;
* Registro do histórico;
* Análise do consumo;
* Geração de informações para previsão de falta de água;
* Visualização por meio de dashboards.

---

## 📊 Dashboard

O dashboard será utilizado para apresentar os dados coletados pelo sistema de maneira organizada e de fácil interpretação.

### Informações previstas

* 💧 Nível atual do reservatório;
* 📈 Histórico do nível de água;
* 📊 Consumo ao longo do tempo;
* ⚠️ Indicação de nível crítico;
* 🔮 Informações relacionadas à previsão de falta de água;
* 📅 Histórico de medições.

### Exemplo conceitual

```text
┌─────────────────────────────────────────────────┐
│              MONITORAMENTO DE ÁGUA              │
├─────────────────────────────────────────────────┤
│                                                 │
│  Nível atual        Consumo       Status        │
│     XX %            XX L/dia      NORMAL        │
│                                                 │
├─────────────────────────────────────────────────┤
│                                                 │
│        Histórico do nível do reservatório       │
│                                                 │
│  100% ┤       ╭──────╮                          │
│   75% ┤───────╯      ╰──────╮                   │
│   50% ┤                       ╰──────            │
│   25% ┤                              ╰──         │
│    0% └──────────────────────────────────        │
│                                                 │
├─────────────────────────────────────────────────┤
│  Previsão: acompanhamento do abastecimento      │
└─────────────────────────────────────────────────┘
```

---

## 🧠 Previsão de Falta de Água

Uma das funcionalidades propostas pelo projeto é utilizar o histórico de dados para identificar padrões relacionados ao consumo e ao nível do reservatório.

A partir dessas informações, o sistema poderá auxiliar na identificação de situações em que o volume disponível esteja se aproximando de uma condição crítica.

```text
Dados históricos
       │
       ▼
┌──────────────────┐
│ Análise dos dados │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ Padrão de consumo │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ Estimativa futura │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ Possível falta    │
│     de água       │
└──────────────────┘
```

> **Observação:** a metodologia utilizada para a previsão será definida e documentada conforme a evolução do projeto.

---

## 📈 Progresso do Projeto

### Progresso geral

**0% concluído**

```text
░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  0%
```

### Etapas do desenvolvimento

| Etapa                            | Status |
| -------------------------------- | :----: |
| Levantamento do problema         |    ⬜   |
| Definição dos requisitos         |    ⬜   |
| Definição da arquitetura         |    ⬜   |
| Definição do hardware            |    ⬜   |
| Desenvolvimento do circuito      |    ⬜   |
| Desenvolvimento do firmware      |    ⬜   |
| Comunicação entre os componentes |    ⬜   |
| Estruturação dos dados           |    ⬜   |
| Desenvolvimento do dashboard     |    ⬜   |
| Implementação da previsão        |    ⬜   |
| Integração do sistema            |    ⬜   |
| Testes                           |    ⬜   |
| Validação                        |    ⬜   |
| Documentação                     |    ⬜   |

**Legenda:**
`⬜` Não iniciado · `🟨` Em andamento · `🟩` Concluído

---

## 🗂️ Estrutura do Projeto

```text
.
├── README.md
│
├── firmware/
│   ├── src/
│   └── ...
│
├── hardware/
│   ├── esquematico/
│   └── ...
│
├── dashboard/
│   └── ...
│
├── docs/
│   ├── arquitetura/
│   └── ...
│
└── tests/
    └── ...
```

> A estrutura de diretórios será ajustada de acordo com a organização definitiva do código e dos documentos.

---

## 🚀 Instruções Básicas de Execução

### Pré-requisitos

Antes de executar o projeto, serão necessárias as ferramentas e dependências definidas para o desenvolvimento do firmware, sistema de dados e dashboard.

### Configuração

```text
1. Clonar o repositório
2. Configurar o ambiente de desenvolvimento
3. Configurar o ESP32
4. Configurar os componentes do sistema
5. Configurar a comunicação
6. Configurar o sistema de dados
```

### Execução

```text
1. Conectar o ESP32
2. Iniciar o firmware
3. Verificar a aquisição dos dados
4. Iniciar os serviços necessários
5. Acessar o dashboard
6. Verificar os dados do reservatório
```

---

## 🧪 Testes e Validação

Os testes serão realizados para verificar o funcionamento individual e integrado dos componentes do sistema.

### Testes previstos

* [ ] Teste de leitura dos sensores;
* [ ] Teste do ESP32;
* [ ] Teste de comunicação;
* [ ] Teste de armazenamento;
* [ ] Teste do dashboard;
* [ ] Teste de identificação de nível crítico;
* [ ] Teste da previsão de falta de água;
* [ ] Teste integrado do sistema;
* [ ] Validação dos resultados.

---

## 📚 Documentação

A documentação do projeto será complementada durante o desenvolvimento, incluindo:

* Arquitetura do sistema;
* Especificação do hardware;
* Funcionamento do firmware;
* Estrutura dos dados;
* Funcionamento do dashboard;
* Metodologia de previsão;
* Procedimentos de instalação e execução;
* Resultados dos testes.

---

## 📌 Status do Projeto

> 🟡 **Em desenvolvimento**

O projeto encontra-se em fase inicial de desenvolvimento. As funcionalidades, componentes e detalhes técnicos serão atualizados conforme as etapas de implementação forem concluídas.

---

## 👨‍💻 Equipe

**Marcos Belo · Jefferson Amorim · Tácito Juno**

**Sistema embarcado baseado em ESP32 para monitoramento inteligente de caixas d'água e cisternas.**
