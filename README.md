# Desafio: Transformação de Dados e Relatório de RH no Power BI 📊

## Objetivo
Este projeto consiste na aplicação de técnicas de Extração, Transformação e Carga (ETL) utilizando o Power Query, culminando na criação de um relatório gerencial de Recursos Humanos no Power BI.

## 1. Etapas de Processamento (Power Query)
Para limpar e modelar os dados conforme as diretrizes do desafio, as seguintes etapas foram realizadas:
- ✔️ **Tipos de Dados:** Conversão da coluna de Salário para o tipo *Número Decimal*.
- ✔️ **Tratamento de Nulos:** Identificação dos gestores através dos valores nulos na coluna `Super_ssn`.
- ✔️ **Divisão e Mescla de Colunas:** Separação do campo "Address" por delimitadores. Além disso, as colunas de primeiro e último nome foram mescladas na nova coluna `Nome_Completo`.
- ✔️ **Mescla de Tabelas (Merge):** 
  - Tabela *Employee* mesclada com *Department* para trazer os nomes dos departamentos.
  - Tabela *Department* mesclada com *Dept_Locations* para criar combinações únicas de localidade.
  - Tabela *Employee* mesclada com ela mesma para vincular o nome dos colaboradores aos respectivos nomes de seus gerentes.
- ✔️ **Limpeza:** Eliminação de todas as colunas de identificadores (IDs) que não seriam utilizadas no visual.

## 2. Construção do Relatório Visual
A partir da base de dados modelada (Star Schema inicial), foi desenvolvido um painel interativo (Dashboard) contendo:
*   **Total de Colaboradores:** Visual do tipo "Cartão" exibindo a contagem total do quadro de funcionários.
*   **Custo com Folha por Departamento:** Gráfico de Barras agrupadas analisando o total da coluna `Salary` por `Dname` (Departamento).
*   **Distribuição de Gênero:** Gráfico de Pizza segmentando o quadro de funcionários.
*   **Filtros de Localização:** Segmentador de dados utilizando a coluna `Dlocation` para gerar interatividade no painel.

## 💡 Pergunta Teórica Obrigatória do Desafio
**Por que, na junção de departamento e localização, utilizamos a opção "Mesclar" e não "Atribuir/Acrescentar"?**
*Resposta:* A função **Mesclar (Merge)** atua como um *JOIN* relacional, conectando colunas diferentes lado a lado através de uma chave correspondente (ID do Departamento). A função **Atribuir (Append)**, por outro lado, serve para empilhar registros (linhas) de tabelas que possuem a mesma estrutura de colunas, o que não atende ao cenário onde precisávamos combinar dados de naturezas distintas.

## Como acessar
O projeto completo (Power Query e Visuais) está contido no arquivo `.pbix` localizado na raiz deste repositório.
