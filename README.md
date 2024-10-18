#### ÚLTIMA ATUALIZAÇÃO (09/10/2024)

# Tabela de Candidatos 2024 (SQL)

Este repositório foi criado para fins educativos e contém uma tabela em SQL gerada a partir dos arquivos de dados de CNPJs fornecidos pelo Tribunal Superior Eleitoral (TSE). A tabela reflete as informações contidas nos arquivos `cnpj_partido_2024.txt` e `cnpj_candidatos_2024.txt`, que serão atualizados conforme novas versões sejam disponibilizadas. 

Todas as informações disponibilizadas neste repositório são públicas e estão acessíveis no próprio site do TSE, podendo ser consultadas por qualquer pessoa interessada.<br>
https://dadosabertos.tse.jus.br/dataset/prestacao-de-contas-eleitorais-2024/resource/47f4ff69-c50a-4c4f-805a-f03336a06cfd 

## Estrutura da Tabela

A tabela armazena informações dos candidatos e partidos, organizadas nas seguintes colunas:

- **id**: Identificador único e incremental de cada registro.
- **tipo_prestador**: Campo inteiro que indica o tipo de registro:
  - `1`: Candidato
  - `2`: Partido
- **cnpj**: CNPJ correspondente ao candidato ou partido.
- **nome**: Nome do candidato ou partido.
- **cnae**: Código CNAE (Classificação Nacional de Atividades Econômicas) relacionado ao registro.
- **created_at**: Data e hora de inserção do registro no banco de dados.

## Atualizações

Os dados serão atualizados conforme novas versões dos arquivos forem publicadas. A tabela será mantida atualizada para refletir quaisquer alterações nos registros de candidatos e partidos.

## Fontes de Dados

Os dados utilizados são extraídos diretamente dos seguintes arquivos de CNPJs fornecidos pelo TSE:
- `cnpj_partido_2024.txt`
- `cnpj_candidatos_2024.txt`

## Estrutura dos arquivos disponibilizados pelo TSE

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

## Como Usar

Clone o repositório e importe o arquivo SQL para seu banco de dados para realizar consultas utilizando os dados disponíveis.

```bash
git clone https://github.com/usuario/repo-candidatos-2024
