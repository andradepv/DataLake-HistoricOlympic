# 🏅 Data Lake: Olimpíadas Paris 2024 & Histórico

Este repositório contém o projeto de construção de um **Data Lake Local** baseado na Arquitetura Medallion (Raw, Bronze e Gold). O objetivo do projeto é ingerir, processar e analisar dados das Olimpíadas de Paris 2024 cruzando-os com o contexto histórico dos Jogos Olímpicos.

## 🏗️ Arquitetura do Data Lake

O pipeline de dados foi desenhado para processar arquivos em etapas, otimizando o armazenamento e garantindo a qualidade da informação:

* **🟤 Camada Raw (`data/raw/`):** Contém os dados brutos (arquivos `.csv`) extraídos do Kaggle. Estes dados refletem exatamente a fonte original, acompanhados de seus respectivos metadados em `.json`.
* **🥈 Camada Bronze (`data/bronze/`):** Os dados brutos foram convertidos para o formato colunar **Apache Parquet**, garantindo alta performance de leitura e compressão. Esta camada também contém um dataset integrado resultante de um **JOIN** entre os dados de Paris e o histórico olímpico.
* **🥇 Camada Gold (`data/gold/`):** Contém os Produtos de Dados (Data Products) finais, prontos para consumo por áreas de negócio. Separados por contexto de análise:
    * `analise_medalhas/`: Quadro de medalhas oficial do Top 10 países.
    * `analise_modalidades/`: Distribuição de medalhas por esportes.

## 🚀 Como Executar o Projeto

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/andradepv/DataLake-HistoricOlympic
   cd DataLake-HistoricOlympic
Instale as dependências:
Certifique-se de ter o Python 3.11+ instalado.

Bash
pip install -r requirements.txt
(Dependências principais: pandas, pyarrow, matplotlib)

Geração dos Dados:
Os códigos de transformação e análise encontram-se em notebooks Python (.ipynb) dentro das respectivas pastas da camada Gold. Basta executá-los em sequência para recriar as bases em .parquet e os relatórios visuais.

📄 Metadados
Todos os datasets do projeto são documentados através de arquivos JSON. O padrão de chaves utilizado pode ser consultado no arquivo metadata_schema.json na raiz do projeto.

👨‍💻 Autor
Paulo Victor Souto De Andrade Estudante de Engenharia de Computação - Universidade do Estado do Amazonas (UEA)

Manaus, AM.