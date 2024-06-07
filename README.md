# Data Analysis

Data Analysis é um projeto desenvolvido para me introduzir à área de análise de dados utilizando Python. A base de dados utilizada neste projeto é fictícia e foi obtida do Kaggle. Este projeto serviu como um exercício prático para aprender e aplicar técnicas de análise de dados. Este projeto foi desenvolvido em Jupyter Notebook para ter uma fácil visualização dos outputs do projeto.

## Descrição

O Data Analysis permite importar uma base de dados, realizar um tratamento inicial, analisar e visualizar dados através de gráficos. O foco principal é a categorização e visualização dos dados para obter insights significativos.

## Funcionalidades

- Importação de base de dados em formato CSV.
- Tratamento de dados, incluindo remoção de colunas desnecessárias e valores nulos.
- Descrição estatística dos dados.
- Contagem e percentual de categorias.
- Criação de gráficos interativos para visualização de dados.

## Tecnologias Utilizadas

- Python 3
- Biblioteca `tkinter` para seleção de arquivo.
- Biblioteca `pandas` para manipulação e análise de dados.
- Biblioteca `plotly` para visualização de dados.

## Código

```python
from tkinter.filedialog import askopenfilename
import pandas as pd
import plotly.express as px

database = 'C:/Users/gamej/OneDrive/Área de Trabalho/Data-Analysis---Projeto-Python/src/example_database/ClientesBanco.csv'

database_import = pd.read_csv(database, encoding='latin1')
pd.set_option('display.max_columns', None) # tira o limite de colunas na visualização
display(database_import)

# Tratamento

database_import = database_import.drop('CLIENTNUM', axis=1) 
# print(database_import)

# display(database_import.info()) 

database_import = database_import.dropna() # aqui estamos excluindo TODOS os valores vazios

# display(database_import.info())

display(database_import.describe().round(2))

value_CxC = database_import['Categoria'].value_counts()
display(value_CxC)
percent_CxC = database_import['Categoria'].value_counts(normalize=True)
display(percent_CxC)

for i in database_import:
    grafico = px.histogram(database_import, x= i, color='Categoria')
    grafico.show()
```

## Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues e pull requests para melhorias ou correções.

## Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## Contato

Se você tiver dúvidas ou sugestões, sinta-se à vontade para me contatar.

## Conecte-se comigo

[![Gmail](https://img.shields.io/badge/Gmail-333333?style=for-the-badge&logo=gmail&logoColor=red)](mailto:juniorbmelo12@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/alexsandro-junior-576719297/)
[![Instagram](https://img.shields.io/badge/-Instagram-%23E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/juniorbm.wn/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/junioom)

