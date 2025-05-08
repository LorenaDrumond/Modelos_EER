# 📊 Modelagem de Dados - Exemplos e Práticas

Este repositório contém exemplos de **modelagem de dados** para diferentes contextos, focando na representação de **entidades, atributos e relacionamentos** em **bancos de dados relacionais**. Os modelos apresentados podem ser utilizados para **aprendizado, prática profissional e projetos acadêmicos**.

---

## 🗂 **Conteúdo**

O repositório inclui os seguintes modelos de dados:

| 🖼 Arquivo                                  | 📄 Descrição                                                       |
|---------------------------------------------|--------------------------------------------------------------------|
| `Modelo_Banco_Claro.jpg` / `Modelo_Banco_Escuro.png` | Estrutura de banco, pessoa, companhia e proprietário, com atributos como CPF, CNH e endereço. |
| `Modelo_Consulta_Medica.png`                | Estrutura para gerenciamento de consultas médicas, incluindo entidades como médico, paciente, exame e consulta. |
| `Modelo_Ordem_MySQL.png`                    | Sistema de ordem de serviço, cobrindo pedidos, análises, responsáveis e departamentos. |
| `Modelo_Universidade.png`                   | Modelo acadêmico abrangendo alunos, professores, cursos, disciplinas, matrículas e períodos letivos. |
| `Modelo_e-commerce_MySQL.png`               | Sistema de e-commerce completo, incluindo cliente, vendedor, produto, pagamento, pedido e entrega. |

---

## ✨ **Objetivos**

✅ Criar **diagramas de entidade-relacionamento (ER)** claros e bem organizados;  
✅ Representar corretamente **entidades, atributos e relacionamentos**;  
✅ Aplicar **conceitos de normalização** e garantir **integridade referencial**;  
✅ Demonstrar **exemplos práticos** aplicáveis a sistemas como bancos, lojas online e ordens de serviço;  
✅ Testar **ferramentas de modelagem** para construção de diagramas ER.

---

## 🏗 Modelos Detalhados

### 🏦 Modelo Banco
- **Entidades:** Banco, Pessoa, Companhia, Proprietário (`Owner`)
- **Atributos:** 
  - `Banco`: `Nome`, `Endereço`  
  - `Pessoa`: `CPF`, `CNH`, `Nome`, `Endereço`  
  - `Companhia`: `Nome`, `Endereço`
- **Relacionamentos:**  
  - Pessoa e Companhia se conectam ao Banco.  
  - Um elemento unificador (`U`) define a entidade Owner.  
- **Uso:**  
  - Estrutura básica para sistemas bancários, permitindo o gerenciamento de clientes e empresas.

---

### 🩺 Modelo Consulta Médica
- **Entidades:** Consulta, Médico, Paciente, Exame
- **Atributos:**  
  - `Consulta`: `IdConsulta`, `IdMedico`, `IdPaciente`, `IdExame`  
  - `Médico`: `IdMedico`, `Nome`, `CRM`, `Especialidade`  
  - `Paciente`: `IdPaciente`, `Nome`, `Endereço`, `Telefone`, `Data de Nascimento`  
  - `Exame`: `IdExame`, `Nome`, `Data`  
- **Relacionamentos:**  
  - A tabela **Consulta** atua como entidade central, ligando Médico, Paciente e Exame por meio de chaves estrangeiras.  
- **Uso:**  
  - Estrutura ideal para **sistemas hospitalares e agendamento de consultas médicas**.

---

### 🛠 Modelo Ordem de Serviço
- **Entidades:** Cliente, Pedido, Ordem de Serviço, Análise de Pedido, Responsável, Departamento
- **Atributos:**  
  - `Cliente`: `IdCliente`, `Nome`, `Contato`  
  - `Pedido`: `IdPedido`, `Data`, `Status`  
  - `Ordem de Serviço`: `IdOrdem`, `IdPedido`, `Descrição`, `Data`  
  - `Análise de Pedido`: `IdAnalise`, `IdPedido`, `Resultado`  
  - `Responsável`: `IdResponsavel`, `Nome`, `Departamento`  
  - `Departamento`: `IdDepartamento`, `Nome`  
- **Relacionamentos:**  
  - Cliente gera pedido.  
  - Pedido gera ordem de serviço.  
  - Análises realizadas por responsáveis de departamentos.  
- **Uso:**  
  - **Aplicação ideal** para sistemas de atendimento ou suporte (help desk).

---

### 🎓 Modelo Universidade
- **Entidades:** Pessoa, Aluno, Professor, Departamento, Disciplina, Curso, Matrícula, Extensão, Pré-requisitos, Período
- **Atributos:**  
  - `Pessoa`: `IdPessoa`, `Nome`, `CPF`, `Endereço`, `Telefone`, `E-mail`  
  - `Aluno`: `IdAluno`, `Pessoa_idPessoa`, `Matrícula`  
  - `Professor`: `IdProfessor`, `Departamento_idDepartamento`, `Pessoa_idPessoa`, `Registro`  
  - `Departamento`: `IdDepartamento`, `Nome`, `Campus`, `IDProfessor_Coordenador`  
  - `Disciplina`: `IdDisciplina`, `Professor_idProfessor`, `Matrícula_idMatrícula`  
  - `Curso`: `IdCurso`, `Departamento_idDepartamento`, `Matrícula_idMatrícula`  
  - `Matrícula`: `IdMatrícula`, `Aluno_idAluno`  
  - `Extensão`: `IdExtensão`, `Nome`, `Área`, `Instituição`, `Matrícula_idMatrícula`  
  - `Pré-requisitos`: `IdPré-requisitos`, `Nome`  
  - `Período`: `IdPeríodo`, `Ano`, `Semestre`  
- **Relacionamentos:**  
  - Alunos e professores vinculados a disciplinas e cursos.  
  - Matrículas ligadas a períodos letivos e extensões acadêmicas.  
  - Pré-requisitos exigidos para determinadas disciplinas.  
- **Uso:**  
  - **Ideal para sistemas acadêmicos**, permitindo o gerenciamento eficiente de alunos, professores, disciplinas e cursos.

---

### 🛒 Modelo E-commerce
- **Entidades:** Cliente, Vendedor, Produto, Estoque, Plataforma, Pedido, Pagamento, Entrega
- **Atributos:**  
  - `Cliente`: `IdCliente`, `Nome`, `Endereço`, `Contato`  
  - `Vendedor`: `IdVendedor`, `Nome`, `Loja`  
  - `Produto`: `IdProduto`, `Nome`, `Preço`, `Categoria`  
  - `Estoque`: `IdEstoque`, `IdProduto`, `Quantidade`  
  - `Plataforma`: `IdPlataforma`, `Nome`, `URL`  
  - `Pedido`: `IdPedido`, `IdCliente`, `Data`, `Status`  
  - `Pagamento`: `IdPagamento`, `IdPedido`, `Método`, `Valor`  
  - `Entrega`: `IdEntrega`, `IdPedido`, `Endereço`, `Status`  
- **Relacionamentos:**  
  - Plataforma disponibiliza produtos.  
  - Cliente adquire produtos via pedidos.  
  - Pedido relacionado a pagamento e entrega.  
- **Destaques:**  
  - Suporte a **múltiplas formas de pagamento** (Pix, boleto, cartão).  
  - **Controle de estoque** e **rastreamento de pedidos**.  

---

## 🧑‍💻 **Como Usar**
Esses modelos podem ser utilizados para:
- **Criação de bases de dados** em MySQL, PostgreSQL, SQL Server, etc.
- **Estudo e prática** de modelagem de dados em cursos e treinamentos.
- **Desenvolvimento de software** exigindo controle de entidades e relacionamentos.

---

## 📌 **Requisitos**
Para utilizar os modelos, será necessário conhecimento básico em **bancos de dados relacionais** e acesso a ferramentas de modelagem:

### 🔧 **Ferramentas Utilizadas**
- **Modelo Consulta Médica:** [DB Designer](https://app.dbdesigner.net/dashboard)
- **Modelo Banco:** [Draw.io](https://app.diagrams.net)
- **Modelos E-commerce, Ordem e Universidade:** [MySQL Workbench](https://www.mysql.com/products/workbench/)

---

## 📖 **Referências**
- Conceitos de **modelagem ER**
- **Normalização de dados** para otimização de tabelas
- Modelagem **lógica e física** para bancos relacionais

---

### 📚 **Bootcamp**
Este projeto faz parte do Bootcamp [Database Experience](https://web.dio.me/track/database-experience).
