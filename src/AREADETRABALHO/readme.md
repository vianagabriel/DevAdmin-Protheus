# Áreas de Trabalho (WorkArea)


## Componentes Disponíveis por Área de Trabalho
- **Tabelas de Banco de Dados Relacionais:** Oracle, Postgres, SQL Server, etc.
- **Arquivos de Bancos Não Relacionais:** CTREE, BTRIEVE, etc.
- **Arquivos Temporários de Dados**
- **Resultado de Consultas SQL**
- **Leitura de Arquivos Texto**

## Identificação por Alias
Cada área de trabalho é identificada por um Alias, como:
- Tabelas de banco de dados: `SA1`, `SA2`, `SB1`, `AA1`, etc.
- Arquivos de trabalho temporários: `TRB`, etc.
- Consultas SQL: `SCN0000001`, etc.

## Campos de Tabelas de Banco de Dados
Os campos das tabelas de banco de dados são definidos de acordo com o Alias, por exemplo:
- `SA1` - Cadastro de clientes: `A1_EMAIL` -> Email do Cliente
- `AA1` - Cadastro de atendentes: `AA1_EMAIL` -> Email do Atendente

## RDD (Replaceable Database Drivers)
Cada área de trabalho possui um RDD para comunicação com diferentes tipos de fontes de dados, incluindo:
- `TOPCONN`: Comunicação com banco de dados relacional via DBACCESS
- `DBFCDX`: Comunicação com arquivos físicos no formato DBF
- `SQLITE`: Comunicação com bancos de dados SQLITE
- `CTREECDX`: Comunicação com arquivos físicos no formato CTREE

## Características
- **Sem Relacionamentos por Chave Estrangeira**
- **Índices Diversos:** Um único índice definido com chave primária baseada no RECNO (`R_E_C_N_O`)
- **Índices com Campo Filial:** Índices sempre levam em conta o campo filial da tabela (`A1_FILIAL + A1_COD + A1_LOJA`)
- **Não Trabalham com Deleção Física por Padrão:** Controle feito através de `D_E_L_E_T_` e `R_E_C_D_E_L_`
- **Interações:** Realizadas através de funções ADVPL/TLPP, incluindo:
  - `DBSELECTAREA`
  - `DBSETORDER`
  - `DBUSERAREA`
  - `DBSEEK`
  - `DBSKIP`
  - `DBGOTO`
  - `DBCLOSEAREA`
  - `MPSYSOPENQUERY`

Este README fornece uma visão geral do sistema de áreas de trabalho, suas características e componentes.
