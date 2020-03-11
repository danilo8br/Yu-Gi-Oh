# Yu-Gi-Oh
- Análise de dados das cartas do anime Yu-Gi-Oh utilizando Python e a biblioteca Pandas

![yugioh](https://user-images.githubusercontent.com/51414398/76413026-709dcc80-6373-11ea-851a-83b4d50b0194.jpg)

- Utilizei um Dataset do site Kiggle do anime Yu-Gi-Oh, no Dataset vem todas as cartas do anime contendo o nome da carta, tipo, level, tipo efeito, elementos, ataque, defesa e o total que é a tabela que eu criei que está somando ataque mais a defesa de todas as cartas.

- Comecei pegando as dez cartas mais fortes dos dados e em seguida fui pegando as dez cartas mais fortes de cada elemento, e para finalizar somei o total de cartas de cada elemento e mostrei em gráficos a quantidade.<h1>



#### Módulos

Os primeiros códigos a seguir fazem importação de duas bibliotecas

<details><summary>Pandas</summary>
Este módulo tem a função de trazer ferramentas para analise de dados.
</details>

```
import pandas as pd
```
<details><summary>Gráficos</summary>
Este módulo serve para fazer exibição de gráficos conforme as estatísticas dos seus dados.
</details>

```
import matplotlib.pyplot as plt
```

#### Leitura

<details><summary>Leitura de arquivos</summary>
Aqui está criando uma variável, em seguida faz a leitura do arquivo.
</details>

```
df = pd.read_csv('card_data.csv')
```

#### Colunas

<details><summary>Pritando colunas</summary>
Aqui está printando as colunas do arquivo.
</details>

```
print(df.columns)
```














## Enjoy :)!
