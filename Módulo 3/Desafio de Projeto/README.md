
# Criando um Dashboard Corporativo com Integração com MySQL e Azure


Este projeto pertence a  "Formação Power BI Analyst" da DIO.
O objetivo é criar um banco de dados MySQL em um servidor externo e estabelecer uma conexão com o Power BI. 
As transformações foram executadas no Power Query e um relatório visual foi criado.

## Tabelas Criadas no Banco de Dados MySQL

- **employee**
- **departament**
- **dept_locations**
- **project**
- **works_on**
- **dependent**

## Diretrizes para Transformação dos Dados

### 1. Verificação dos Cabeçalhos e Tipos de Dados

#### employee
| Nome     | Tipo de Dados   |
|----------|-----------------|
| Fname    | varchar(15)     |
| Minit    | char(1)         |
| Lname    | varchar(15)     |
| Ssn      | char(9)         |
| Bdate    | date            |
| Address  | varchar(30)     |
| Sex      | char(1)         |
| Salary   | decimal(10,2)   |
| Super_ssn| char(9)         |
| Dno      | int(11)         |

#### departament
| Nome            | Tipo de Dados   |
|-----------------|-----------------|
| Dname           | varchar(15)     |
| Dnumber         | int(11)         |
| Mgr_ssn         | char(9)         |
| Mgr_start_date  | date            |
| Dept_create_date| date            |

#### dept_locations
| Nome     | Tipo de Dados   |
|----------|-----------------|
| Dnumber  | int(11)         |
| Dlocation| varchar(15)     |

#### project
| Nome     | Tipo de Dados   |
|----------|-----------------|
| Pname    | varchar(15)     |
| Pnumber  | int(11)         |
| Plocation| varchar(15)     |
| Dnum     | int(11)         |

#### works_on
| Nome     | Tipo de Dados   |
|----------|-----------------|
| Essn     | char(9)         |
| Pno      | int(11)         |
| Hours    | decimal(3,1)    |

#### dependent
| Nome           | Tipo de Dados   |
|----------------|-----------------|
| Essn           | char(9)         |
| Dependent_name | varchar(15)     |
| Sex            | char(1)         |
| Bdate          | date            |
| Relationship   | varchar(8)      |

### 2. Modificação dos Valores Monetários
- Coluna `salary` da tabela `employee` foi modificada para o tipo `Número Decimal Fixo`.

### 3. Verificação e Análise de Nulos
- Campo nulo localizado não foi removido.
- Registros com campos nulos: `employee` - Campo `Super_ssn` para o registro com `Ssn 888665555`.


### 4. Separação de Colunas Complexas
- Coluna `Address` da tabela `employee` foi separada.

### 5. Mescla de Consultas
- Mescla de `employee` e `departament`:
- Trouxe somente a coluna Dname para a tabela employee

### 6. Junção de Colaboradores e Respectivos Gerentes
- Criei uma coluna usando DAX utilizando a função LOOKUPVALUE retornando os gerentes dos colaboradores

### 7. Mescla de Nome e Sobrenome dos Colaboradores
- Realizei a Mescla da coluna Fname com Lname.


### 8. Eliminação de Colunas Desnecessárias
- As colunas desnecessárias foram removidas de cada tabela.

## Conclusão
Um projeto simples, guiado pela professora Juliana Mascarenhas, 
Através dele, foram aplicados conceitos de integração, transformação e visualização de dados utilizando Azure , MySQL e Power BI.
