# 🔧 Projeto de Modelagem de Dados – Oficina Mecânica  

## 📝 Descrição do Desafio  
Este projeto consiste na criação de um **esquema conceitual de banco de dados para um sistema de controle e gerenciamento de ordens de serviço em uma oficina mecânica**, desenvolvido a partir de uma narrativa fornecida.  

O objetivo é identificar **entidades, atributos e relacionamentos** necessários para atender os requisitos do sistema.  

O esquema deverá ser adicionado a este repositório no **GitHub** para avaliação como parte de um **desafio de projeto**.  

---

## 🎯 Objetivo  
Criar um **esquema conceitual** (modelo EER) para o contexto de **oficina mecânica**, com base na seguinte narrativa:  

- Clientes levam veículos à oficina para consertos ou revisões periódicas.  
- Cada veículo é designado a uma equipe de mecânicos, que identifica os serviços a serem executados e preenche uma **Ordem de Serviço (OS)** com data de entrega.  
- A partir da OS, calcula-se o valor de cada serviço, consultando-se uma **tabela de referência de mão de obra**.  
- O valor de cada peça também compõe a OS.  
- O cliente autoriza a execução dos serviços.  
- A mesma equipe avalia e executa os serviços.  
- Os mecânicos possuem: código, nome, endereço e especialidade.  
- Cada OS possui: número, data de emissão, valor, status e data de conclusão.  

---

## 📐 Modelo Conceitual  

### Entidades e atributos identificados:  

- **Cliente**  
  - ID_Cliente  
  - Nome  
  - Endereço  
  - Telefone  

- **Veículo**  
  - ID_Veiculo  
  - Placa  
  - Modelo  
  - Ano  
  - FK → Cliente  

- **Mecânico**  
  - ID_Mecanico  
  - Nome  
  - Endereço  
  - Especialidade  

- **Equipe**  
  - ID_Equipe  
  - Nome da Equipe  

- **Ordem_Servico (OS)**  
  - ID_OS  
  - Data_Emissao  
  - Data_Conclusao  
  - Status  
  - Valor_Total  
  - FK → Veículo  
  - FK → Equipe  

- **Servico**  
  - ID_Servico  
  - Descrição  
  - Valor_Referencia  

- **Peca**  
  - ID_Peca  
  - Descrição  
  - Valor  

- **Itens_Servico (relacionamento OS x Serviço)**  
  - FK → Ordem_Servico  
  - FK → Servico  
  - Quantidade  
  - Valor_Total  

- **Itens_Peca (relacionamento OS x Peça)**  
  - FK → Ordem_Servico  
  - FK → Peca  
  - Quantidade  
  - Valor_Total  

---

## 🔗 Relacionamentos principais  

- **Cliente** possui **um ou mais Veículos**.  
- **Veículo** gera **uma ou mais Ordens de Serviço**.  
- **Ordem de Serviço** pode conter **vários Serviços** e **várias Peças**.  
- O valor da OS é calculado pela soma de **Serviços + Peças**.  

---

## 🛠️ Ferramentas Utilizadas  
- **SQL Workbench** para criação do esquema.  
- **MySQL** como SGBD de referência.  
- **Git/GitHub** para versionamento e publicação do projeto.  

---

