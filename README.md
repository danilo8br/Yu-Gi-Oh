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

<details><summary>Colunas do arquivo</summary>
Aqui mostra toda as colunas que contém no arquivo.
</details>

```
print(df.columns)
```

<details><summary>Colunas e os dados</summary>
 Aqui mostra uma lista dentro de outra chamando cada coluna do arquivo para mostrar seus dados.
</details>

```
df[['Name', 'Type', 'Level', 'Race', 'Attribute', 'ATK', 'DEF']]
```

<details><summary>Nova coluna</summary>
Criando uma coluna que esta recebendo o ataque mais a defesa para cada carta.
</details>

```
df['Total'] = df['ATK'] + df['DEF']
```

#### Ordenando valores

<details><summary>As cartas mais fortes</summary>
Ordenando os valores do maior pro menor e pegando as 10 cartas mais fortes do arquivo.
</details>

```
df.sort_values('Total', ascending=False).iloc[0:10]
```

<details><summary>Elemento Escuridão</summary>
Essas são as 10 cartas mais fortes do elemento Escuridão.
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Attribute'] == 'DARK')].iloc[0:10]
```

<details><summary>Elemento Luz</summary>
Essas são as 10 cartas mais fortes de elemento Luz.
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Attribute'] == 'LIGHT')].iloc[0:10]
```

<details><summary>Elemento Divino</summary>
Essas são as 10 cartas mais fortes do elemento Divinas.
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Attribute'] == 'DIVINE')].iloc[0:10]
```

<details><summary>Elemento Terra</summary>
Essas são as 10 cartas de mais fortes de elemento Terra.
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Attribute'] == 'EARTH')].iloc[0:10]
```

<details><summary>Elemento Fogo</summary>
Essas são as 10 cartas mais fortes do elemento Fogo.
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Attribute'] == 'FIRE')].iloc[0:10]
```

<details><summary>Elemento Água</summary>
Essas são as 10 cartas mais fortes de elemento Água.
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Attribute'] == 'WATER')].iloc[0:10]
```

<details><summary>Elemento Vento</summary>
Essas são as 10 cartas mais fortes de elemento Vento.
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Attribute'] == 'WIND')].iloc[0:10]
```


#### Contador

<details><summary>Contando os Elementos</summary>
Contando quantas cartas existem de todos os elementos.
</details>

```
df.groupby(['Attribute']).count()
```

<details><summary>Calculando o total de cartas por elemento</summary>
Calculando quantas cartas de todos elementos.
</details>

```
dark = df[df['Attribute'] == 'DARK'].shape[0]
light = df[df['Attribute'] == 'LIGHT'].shape[0]
divine = df[df['Attribute'] == 'DIVINE'].shape[0]
earth = df[df['Attribute'] == 'EARTH'].shape[0]
fire = df[df['Attribute'] == 'FIRE'].shape[0]
water = df[df['Attribute'] == 'WATER'].shape[0]
wind = df[df['Attribute'] == 'WIND'].shape[0]
```

#### Utilizando os Gráficos

<details><summary>Variáveis Y</summary>
As variáveis armazenando os totais de cartas para acrescentar na parte Y do gráfico.
</details>

```
atributos = [dark, light, divine, earth, fire, water, wind]
```

<details><summary>Variáveis X</summary>
Os nomes de cada elemento para acrescentar na parte X do gráfco.
</details>

```
elementos = ['DARK', 'LIGHT', 'DIVINE', 'EARTH', 'FIRE', 'WATER', 'WIND']
```

<details><summary>Gráfico de Barras</summary>
Aqui está o titulo do gráfico e os eixos.
</details>

```
# Titulo
plt.title('Total de Elementos por Cartas')

#Eixos
plt.xlabel('Elements')
plt.ylabel('Index')

plt.bar(elementos, atributos)
plt.show()
```


## Enjoy :)!
