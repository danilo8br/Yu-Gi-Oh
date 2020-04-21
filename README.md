# Yu-Gi-Oh
- Data analysis of Yu-Gi-Oh anime cards using Python and the Pandas library

![yugioh](https://user-images.githubusercontent.com/51414398/76413026-709dcc80-6373-11ea-851a-83b4d50b0194.jpg)

- I used a Dataset from the Kiggle website of the Yu-Gi-Oh anime, in the Dataset comes all the anime cards containing the name of the card, type, level, effect type, elements, attack, defense and the total that is the table I created which is adding attack plus the defense of all cards.

- I started by taking the ten strongest cards from the dice and then I took the ten strongest cards from each element, and finally I added up the total number of cards for each element and showed in graphs the amount. <h1>



#### Modules

The first codes below import two libraries

<details><summary>Pandas</summary>
This module has the function of bringing tools for data analysis.
</details>

```
import pandas as pd
```
<details><summary>Graphics</summary>
This module is used to display graphs according to the statistics of your data.
</details>

```
import matplotlib.pyplot as plt
```

#### Reading

<details><summary>Reading files</summary>
Here you are creating a variable, then read the file.
</details>

```
df = pd.read_csv('card_data.csv')
```

#### Colums

<details><summary>File columns</summary>
Here it shows all the columns it contains in the file.
</details>

```
print(df.columns)
```

<details><summary>Columns and data</summary>
 Here it shows a list within another one calling each column of the file to show its data.
</details>

```
df[['Name', 'Type', 'Level', 'Race', 'Attribute', 'ATK', 'DEF']]
```

<details><summary>New colum</summary>
 Creating a column that is receiving the attack plus the defense for each card.
</details>

```
df['Total'] = df['ATK'] + df['DEF']
```

#### Sorting values

<details><summary>The strongest cards</summary>
Sorting the values from the highest to the lowest and taking the 10 strongest cards from the file.
</details>

```
df.sort_values('Total', ascending=False).iloc[0:10]
```

<details><summary>Darkness Element</summary>
These are the 10 strongest cards of the Darkness elements

</details>

```
df.sort_values('Total', ascending=False).loc[(df['Attribute'] == 'DARK')].iloc[0:10]
```

<details><summary>Light Element</summary>
These are the 10 strongest Light element cards.
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Attribute'] == 'LIGHT')].iloc[0:10]
```

<details><summary>Divine Element</summary>
 These are the 10 strongest cards in the Divine element.
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Attribute'] == 'DIVINE')].iloc[0:10]
```

<details><summary>Element earth</summary>
 These are the 10 strongest Earth cards.
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Attribute'] == 'EARTH')].iloc[0:10]
```

<details><summary>Fire element</summary>
These are the 10 strongest cards in the Fire element.
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Attribute'] == 'FIRE')].iloc[0:10]
```

<details><summary>Water element</summary>
These are the 10 strongest Water element cards.
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Attribute'] == 'WATER')].iloc[0:10]
```

<details><summary>Wind element</summary>
These are the 10 strongest Wind element cards.
</details>

```
df.sort_values('Total', ascending=False).loc[(df['Attribute'] == 'WIND')].iloc[0:10]
```


#### Counter

<details><summary>Counting the Elements</summary>
Counting how many letters there are of all the elements.
</details>

```
df.groupby(['Attribute']).count()
```

<details><summary>Calculating total cards per element</summary>
Calculating how many cards of all elements.
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

#### Using the Graphics

<details><summary>Y variables</summary>
The variables storing the card totals to add to the Y part of the graph.
</details>

```
atributos = [dark, light, divine, earth, fire, water, wind]
```

<details><summary>X Variables </summary>
The names of each element to be added in part X of the graph.
</details>

```
elementos = ['DARK', 'LIGHT', 'DIVINE', 'EARTH', 'FIRE', 'WATER', 'WIND']
```

<details><summary>Bar Chart</summary>
Here is the title of the graph and the axes.
</details>

```
# Title
plt.title('Total de Elementos por Cartas')

#Axles
plt.xlabel('Elements')
plt.ylabel('Index')

plt.bar(elementos, atributos)
plt.show()
```


## Enjoy :)!
