# 🧪 Prova Técnica – Desenvolvedor Java

## 🎯 Objetivo

Avaliar a capacidade de desenvolver uma API REST utilizando Java, com foco em estrutura de código, modelagem, boas práticas, uso de ferramentas e clareza de raciocínio.

---

## 💼 Desafio Técnico

Desenvolver uma API REST para gerenciamento de **SISTEMA BANCÁRIO**.

### Funcionalidades obrigatórias

- Criar uma conta bancária com:
  - Nome do titular
  - CPF
  - Saldo (deve ser automaticamente iniciado com o valor fixo de **R$ 1.000,00**)
  - Data de abertura

- Consultar saldo de uma conta pelo ID

- Realizar uma transação entre contas:
  - Conta origem
  - Conta destino
  - Valor
  - Data da transação
  - Status (`APROVADA` ao criar)
 
- Implementar validação para impedir transações que excedam o saldo da conta origem

- Listar todas as transações de uma conta específica

- **Executar estorno de uma transação:**
  - O estorno deve inverter a operação original:
    - Debitar o valor da conta destino
    - Creditar o valor na conta origem
  - O estorno só poderá ser realizado se a conta destino possuir saldo suficiente
  - O status da transação original deve ser atualizado para `ESTORNADA`
 
- **Atualização dos status das transações**
  - Toda transação deve possuir um campo de **status**, que pode ser:
    - `APROVADA`
    - `ESTORNADA`
  - Ao realizar uma transação, ela deve ser registrada diretamente com status `APROVADA`
  - Ao executar um estorno, o status da transação original deve ser atualizado para `ESTORNADA`
  - O sistema deve garantir que apenas transações com status `APROVADA` possam ser estornadas
 
- Criar relatório simples contendo:
  - Quantidade total de contas criadas
  - Total de transações realizadas no sistema
  - Valor total movimentado

---

## 🔧 Requisitos Técnicos

Você deve utilizar obrigatoriamente:

- Java 17 **ou** Java 21
- Spring Boot (qualquer versão compatível com Java 17 ou 21)
- Persistência com JPA + banco de dados H2 ou MongoDB (diferencial)
- Validações com Bean Validation
- Mapeamento adequado entre entidades (`Conta`, `Transacao`)
- Testes unitários (JUnit + Mockito)
- Versionamento com Git (repositório público no GitHub)
- README com instruções claras de execução

---

## ✅ Entrega

Você deve entregar:

1. Repositório público no GitHub chamado **`prova-java-sistema-bancario`**

2. Um `README.md` com:
   - Descrição do projeto
   - Como rodar a aplicação (com `mvn` ou `gradle`)
   - Exemplos de requisições (via curl, Postman, etc.)
   - Quais funcionalidades foram implementadas
   - Observações (se houver algo não concluído ou limitações)

---

## 🚫 Regras

- A prova é individual
- O uso de frameworks e bibliotecas auxiliares é permitido, mas evite gerar código automático
- A entrega deve ser feita no prazo combinado
- Qualquer dúvida durante a execução, entre em contato com os avaliadores

---

## 💡 Dica

Organize o projeto como se fosse para produção. Esperamos ver boas práticas como:

- Separação de camadas (`controller`, `service`, `repository`)
- Uso correto de DTOs e entidades
- Tratamento de erros e respostas adequadas da API
- Código limpo e testável
