# salary_analysisKaggle
Análise de treino feita a partir do kaggle

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

read = '/content/Salary_Data.csv'
df1 = pd.read_csv(read)

df1.info()
df1.head()

biggest_salary = df1['Salary'].idxmax()

linha_maior_valor = df1.loc[biggest_salary]
print(linha_maior_valor)

lowest_salary = df1['Salary'].idxmin()

linha_menor_valor = df1.loc[lowest_salary]
print(linha_menor_valor)

# Visulização
Pizza

plt.figure(figsize=(4,4))
df1['Gender'].value_counts().plot(kind='pie',textprops={'color':'b'},autopct='%.2f',cmap='cool')
plt.title('Genders',fontsize=20)
plt.legend(['Male','Female'])
plt.show()

Histograma

plt.figure(figsize=(20,5))
plt.title('AGE X SALARY', fontsize = 15)
plt.xlabel('Age', fontsize = 15)
plt.ylabel('Salary', fontsize = 15)
plt.bar(df1['Age'].sort_values(), df1['Salary'], color='orange')

plt.show()

df1.groupby('Gender').max().plot(kind='bar')
plt.show()

df1.groupby('Age').max().plot(kind='bar')

df1.groupby('Years of Experience').max().plot(kind='bar')

Tirando a media dos valores para cada idade tem um valor correspondente no salario
df1[['Age','Salary']].groupby('Age').mean()


plt.figure(figsize=(20,5))
s = df1[['Age', 'Salary']].groupby('Age').mean()
x = s.index.to_list()
plt.plot(x,y,marker = 'x')

df1[['Gender','Salary']].groupby('Gender').mean()
