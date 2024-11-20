
# AWS EBAC Tutorial

Este repositório contém um guia passo a passo para a realização de atividades práticas na AWS utilizando S3 e Athena.

## Estrutura do Repositório

- **aws_s3/**: Instruções e configurações para criar e gerenciar buckets no AWS S3.
- **aws_athena/**: Instruções para configurar o AWS Athena e executar queries.
- **queries/**: Scripts das queries que devem ser executadas no Athena.
- **results/**: Resultados das queries em formato CSV.

## Pré-requisitos

- Conta ativa na AWS.
- Cartão de crédito vinculado à conta AWS.
- O arquivo `credito-aula.csv` fornecido pela plataforma EBAC.

---

## Passos Principais

### 1. Criar Conta AWS
1. Acesse a [plataforma AWS](https://aws.amazon.com/).
2. Clique em "Criar uma nova conta da AWS".
3. Preencha os dados solicitados e finalize o cadastro.
4. Acesse o console da AWS com suas novas credenciais.

### 2. Configuração AWS S3
1. Acesse o serviço S3.
2. Crie dois buckets com os nomes:
   - `ebac-{seu-nome}-modulo_1` para armazenar os dados.
   - `ebac-{seu-nome}-query-results` para armazenar os resultados.
3. Faça upload do arquivo `credito-aula.csv` no bucket de dados.

### 3. Configuração AWS Athena
1. Acesse o console do Athena.
2. Configure o local de armazenamento das consultas:
   - Vá em `Settings` e preencha o campo `Query result location` com o bucket `ebac-{seu-nome}-query-results`.
3. Salve as configurações.

### 4. Criação e Execução de Queries
1. No console do Athena, execute as queries descritas em [queries/](queries/).
2. Extraia os resultados como CSV e salve na pasta `results/`.

---

## Queries

### Query 1: Seleção de Todos os Clientes
```sql
SELECT * FROM clientes;
```

### Query 2: Seleção de Clientes com Limite de Crédito
```sql
SELECT id, idade, limite_credito FROM clientes WHERE limite_credito > 3000;
```

### Query 3: Média de Idade por Sexo
```sql
SELECT sexo, AVG(idade) AS media_idade_por_sexo FROM clientes GROUP BY sexo;
```

---

## Resultados Esperados

Os resultados para cada query podem ser encontrados na pasta `results/`.

