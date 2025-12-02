#### ÚLTIMA ATUALIZAÇÃO (02/12/2025) | LAST UPDATE (12/02/2025)

# Tabela de Candidatos 2024 (SQL) | 2024 Candidates Table (SQL)


## English

This repository was created for educational purposes and contains an SQL table generated from CNPJ data files provided by the Superior Electoral Court (TSE). The table reflects information contained in the files `cnpj_partido_2024.txt` and `cnpj_candidatos_2024.txt`, which will be updated as new versions become available.

All information provided in this repository is public and accessible on the TSE website, available for consultation by anyone interested.<br>
https://dadosabertos.tse.jus.br/dataset/prestacao-de-contas-eleitorais-2024/resource/47f4ff69-c50a-4c4f-805a-f03336a06cfd

### Table Structure

The table stores information about candidates and political parties, organized in the following columns:

- **id**: Unique and incremental identifier for each record.
- **tipo_prestador**: Integer field indicating the record type:
  - `1`: Candidate
  - `2`: Political Party
- **cnpj**: CNPJ (Brazilian tax ID) corresponding to the candidate or party.
- **nome**: Name of the candidate or party.
- **cnae**: CNAE code (National Classification of Economic Activities) related to the record.
- **created_at**: Date and time of record insertion in the database.

### Updates

The data will be updated as new versions of the files are published. The table will be maintained up-to-date to reflect any changes in candidate and party records.

### Data Sources

The data used is extracted directly from the following CNPJ files provided by TSE:
- `cnpj_partido_2024.txt`
- `cnpj_candidatos_2024.txt`

### TSE File Structure

#### Header Structure
| Position | Field            | Size | Format     | Description                                           |
|----------|------------------|------|------------|-------------------------------------------------------|
| 1-1      | Record           | 1    | NUMERIC    | HEADER record identifier. Fixed "1"                   |
| 2-13     | Generation Date  | 12   | DATE/TIME  | Generation date and time in DDMMYYYYHHMM format       |
| 14-16    | Layout Version   | 3    | NUMERIC    | CNPJ file version. Fixed "100"                        |
| 17-26    | Layout Name      | 10   | ALPHA      | Fixed "CNPJPREST"                                     |
| 27-200   | Blank spaces     | 174  | ALPHA      | Filled with blank spaces                              |

#### Detail Structure
| Position | Field                        | Size | Format     | Description                                                  |
|----------|------------------------------|------|------------|--------------------------------------------------------------|
| 1-1      | Record                       | 1    | NUMERIC    | DETAIL record identifier. Fixed "2"                          |
| 2-3      | Account Provider Type        | 2    | ALPHA      | Provider Type: 01-Party, 02-Candidate                        |
| 4-17     | CNPJ                         | 14   | ALPHA      | Provider's CNPJ                                              |
| 18-167   | Account Provider Name        | 150  | ALPHA      | Fiscal name registered with the Federal Revenue              |
| 168-171  | Legal Nature                 | 4    | ALPHA      | CNPJ Legal Nature                                            |
| 172-178  | Main CNAE                    | 7    | ALPHA      | Registered main CNAE code                                    |
| 179-188  | Blank spaces                 | 10   | ALPHA      | Filled with blank spaces                                     |
| 189-200  | CNPJ insertion date          | 12   | DATE/TIME  | Insertion date and time in DDMMYYYYHHMM format               |

#### Trailer Structure
| Position | Field          | Size | Format     | Description                                                  |
|----------|----------------|------|------------|--------------------------------------------------------------|
| 1-1      | Record         | 1    | NUMERIC    | TRAILER record identifier. Fixed "9"                         |
| 2-10     | Total CNPJs    | 9    | NUMERIC    | Total number of CNPJs in file (excluding HEADER and TRAILER) |
| 11-200   | Blank spaces   | 190  | ALPHA      | Filled with blank spaces                                     |

### How to Use

Clone the repository and import the SQL file into your database to query the available data.

```bash
git clone https://github.com/GuelBandeira/tse-candidatos-sql-2024.git
```

## Português

Este repositório foi criado para fins educativos e contém uma tabela em SQL gerada a partir dos arquivos de dados de CNPJs fornecidos pelo Tribunal Superior Eleitoral (TSE). A tabela reflete as informações contidas nos arquivos `cnpj_partido_2024.txt` e `cnpj_candidatos_2024.txt`, que serão atualizados conforme novas versões sejam disponibilizadas. 

Todas as informações disponibilizadas neste repositório são públicas e estão acessíveis no próprio site do TSE, podendo ser consultadas por qualquer pessoa interessada.<br>
https://dadosabertos.tse.jus.br/dataset/prestacao-de-contas-eleitorais-2024/resource/47f4ff69-c50a-4c4f-805a-f03336a06cfd 

### Estrutura da Tabela

A tabela armazena informações dos candidatos e partidos, organizadas nas seguintes colunas:

- **id**: Identificador único e incremental de cada registro.
- **tipo_prestador**: Campo inteiro que indica o tipo de registro:
  - `1`: Candidato
  - `2`: Partido
- **cnpj**: CNPJ correspondente ao candidato ou partido.
- **nome**: Nome do candidato ou partido.
- **cnae**: Código CNAE (Classificação Nacional de Atividades Econômicas) relacionado ao registro.
- **created_at**: Data e hora de inserção do registro no banco de dados.

### Atualizações

Os dados serão atualizados conforme novas versões dos arquivos forem publicadas. A tabela será mantida atualizada para refletir quaisquer alterações nos registros de candidatos e partidos.

### Fontes de Dados

Os dados utilizados são extraídos diretamente dos seguintes arquivos de CNPJs fornecidos pelo TSE:
- `cnpj_partido_2024.txt`
- `cnpj_candidatos_2024.txt`

### Estrutura dos arquivos disponibilizados pelo TSE

#### Estrutura do Header
| Posição | Campo            | Tamanho | Formato    | Descrição                                             |
|---------|------------------|---------|------------|-------------------------------------------------------|
| 1-1     | Registro          | 1       | NUMÉRICO   | Identificador do registro HEADER. Fixo "1"            |
| 2-13    | Data Geração      | 12      | DATA/HORA  | Data e hora da geração no formato DDMMAAAAHHMM        |
| 14-16   | Versão Leiaute    | 3       | NUMÉRICO   | Versão do arquivo de CNPJs. Fixo "100"                |
| 17-26   | Nome do Leiaute   | 10      | ALFA       | Fixo "CNPJPREST"                                      |
| 27-200  | Espaços em branco | 174     | ALFA       | Preenchimento com espaços em branco                   |

#### Estrutura do Detalhe
| Posição | Campo                        | Tamanho | Formato    | Descrição                                                    |
|---------|------------------------------|---------|------------|--------------------------------------------------------------|
| 1-1     | Registro                      | 1       | NUMÉRICO   | Identificador do registro DETALHE. Fixo "2"                   |
| 2-3     | Tipo de Prestador de Contas   | 2       | ALFA       | Tipo de Prestador: 01-Partido, 02-Candidato                   |
| 4-17    | CNPJ                          | 14      | ALFA       | CNPJ do Prestador                                             |
| 18-167  | Nome do Prestador de Contas   | 150     | ALFA       | Nome fiscal registrado na Receita Federal                     |
| 168-171 | Natureza Jurídica             | 4       | ALFA       | Natureza Jurídica do CNPJ                                     |
| 172-178 | CNAE Principal                | 7       | ALFA       | Código CNAE principal registrado                              |
| 179-188 | Espaços em branco             | 10      | ALFA       | Preenchido com espaços em branco                              |
| 189-200 | Data de inserção do CNPJ      | 12      | DATA/HORA  | Data e hora da inserção no formato DDMΜΑΑΑΑΗΗΜΜ               |

#### Estrutura do Trailer
| Posição | Campo           | Tamanho | Formato    | Descrição                                                    |
|---------|-----------------|---------|------------|--------------------------------------------------------------|
| 1-1     | Registro        | 1       | NUMÉRICO   | Identificador do registro TRAILER. Fixo "9"                   |
| 2-10    | Total de CNPJs  | 9       | NUMÉRICO   | Quantidade total de CNPJs no arquivo (excluindo HEADER e TRAILER) |
| 11-200  | Espaços em branco | 190     | ALFA       | Preenchido com espaços em branco                              |

### Como Usar

Clone o repositório e importe o arquivo SQL para seu banco de dados para realizar consultas utilizando os dados disponíveis.

```bash
git clone https://github.com/GuelBandeira/tse-candidatos-sql-2024.git
```

---
