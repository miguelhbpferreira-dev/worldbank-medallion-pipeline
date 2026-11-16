# Onde colocar os ficheiros no GitHub

O ZIP já está organizado. Extrai-o e envia o conteúdo para a raiz do repositório `worldbank-medallion-pipeline`, preservando as pastas. Não precisas de escrever estes ficheiros manualmente.

| Ficheiro ou pasta | Local no repositório | Função |
| --- | --- | --- |
| `README.md` | Raiz | Apresentação do projeto, com imagens e diagrama já ligados |
| `requirements.txt` | Raiz | Lista de dependências Python |
| `.gitignore` | Raiz | Exclui cache, ambientes e dados gerados dos commits feitos por Git |
| `worldbank_medallion_pipeline.ipynb` | `notebooks/` | Notebook original que forneceste |
| 8 gráficos PNG | `docs/images/` | Imagens originais extraídas dos resultados guardados |
| `pipeline_architecture.png` | `docs/images/` | Diagrama visível no README |
| `pipeline_architecture.svg` | `docs/images/` | Versão vetorial do mesmo diagrama |
| `architecture.mmd` | `docs/` | Fonte editável do diagrama em Mermaid |
| `README.md` dos gráficos | `docs/images/` | Galeria completa e notas de interpretação |

## Conteúdo do requirements.txt

```text
requests
hdfs
pyspark[sql]
pandas
matplotlib
jupyterlab
```

O ficheiro real também inclui comentários sobre compatibilidade. `json`, `datetime` e `pathlib` fazem parte do Python e não precisam de ser instalados por este ficheiro. NumPy não é importado diretamente no notebook, pelo que não foi acrescentado como dependência direta.

As versões exatas das bibliotecas não estão registadas no notebook. Esta lista não é um ambiente testado ou fixado por versão. A versão do PySpark deve corresponder ao ambiente Spark utilizado. Java e Hadoop são requisitos do ambiente; não são instalados pelo `requirements.txt`.

Para instalar os pacotes num ambiente compatível:

```bash
python -m pip install -r requirements.txt
```

## Passos no browser

1. Abre o repositório do projeto no GitHub.
2. Escolhe **Add file → Upload files**, ou a opção de carregar ficheiros se o repositório estiver vazio.
3. Arrasta o conteúdo extraído do ZIP. O README e o requirements devem ficar logo na raiz, não dentro de uma pasta adicional `GitHub_Big_Data`.
4. Confirma que `notebooks/` e `docs/` mantêm a sua estrutura e que `.gitignore` foi incluído.
5. Guarda o commit e abre a página inicial do repositório: o README deve mostrar o diagrama e dois gráficos selecionados. A ligação da galeria abre os 8 gráficos.

Se já tens um README no repositório, substitui-o pelo incluído no pacote para usar as ligações corretas das imagens.

## O que foi gerado e o que continua por validar

- Os 8 gráficos foram extraídos sem alteração; não foram recalculados.
- O diagrama foi criado com base na estrutura e nos passos de armazenamento do código.
- O notebook original foi preservado, incluindo os resultados guardados.
- A sintaxe do código, os caminhos das imagens, os ficheiros e a integridade do ZIP foram verificados.
- O pipeline não foi executado no cluster Hadoop. Mantêm-se os ajustes de configuração e interpretação documentados no README. O gráfico original de saldo aproximado e o índice exploratório estão identificados na galeria.

Referências: [requirements do pip](https://pip.pypa.io/en/stable/reference/requirements-file-format/) e [instalação do PySpark](https://spark.apache.org/docs/latest/api/python/getting_started/install.html).
