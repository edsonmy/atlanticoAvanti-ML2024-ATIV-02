# Atlântico Avanti - Bootcamp Machine Learning (2024)
#
## Atividade 02 (ATIV-02)
##
#### - Tipo: Somativa;
#### - Tema: Algoritmos básicos de programação em linguagem python e visualização e análise de dados.
#### - Conteúdo: Módulo 1 e 2.
#### - Participantes: Individual.
#### - Avaliação do aluno.

#### Objetivo: Avaliar desempenho do aluno sobre conhecimentos básicos de programação em linguagem python e visualização e análise de dados.
#### Nota: 0 a 3 supercrítico, 4 a 6 crítico, 5 a 7 razoável e 8 a 10 bom;
#### Critérios avaliados: Respostas com coerência, coesão e com exemplos.

#### - Informações adicionais: A atividade é composta por 5 questões dissertativas sobre python e 5 questões sobre visualização e análise de dados.

#### - AO CONCLUIR A ATIVIDADE: ENVIAR APENAS O LINK DO REPOSITÓRIO GITHUB (ESPECIFICAR A BRANCH) PÚBLICO.

--------------
## Questões

### 1. Escreva uma função que receba uma lista de números e retorne outra lista com os números ímpares.

    def numeros_impares(lista_numeros):
      numeros_impares = [numero for numero in lista_numeros if numero % 2 != 0]
      return numeros_impares

### 2. Escreva uma função que receba uma lista de números e retorne outra lista com os números primos presentes.

#### Para saber se um número é primo, verifique se ele é divisivel por algum inteiro até a sua raiz quadrada. Se existir algum número que a divisão tem resto = 0, ele não é primo.

    def is_prime(numero):
      if numero <= 1:
        return False
      for divisor in range(2, int(numero**0.5) + 1):
        if numero % divisor == 0:
          return False
      return True

    def numeros_primos(lista_numeros):
      primos = [numero for numero in lista_numeros if is_prime(numero)]
      return primos

### 3. Escreva uma função que receba duas listas e retorne outra lista com os elementos que estão presentes em apenas uma das listas.

    def elementos_unicos(lista1, lista2):
      elementos_unicos = []
      conjunto_lista1 = set(lista1)
      for elemento in lista2:
        if elemento not in conjunto_lista1:
          elementos_unicos.append(elemento)

      for elemento in lista1:
        if elemento not in set(lista2):
          elementos_unicos.append(elemento)

      return elementos_unicos

### 4. Dada uma lista de números inteiros, escreva uma função para encontrar o segundo maior valor na lista.

    def segundo_maior(numeros):
      if len(numeros) <= 1:
        return None
    
      maior_valor = max(numeros)
      numeros.remove(maior_valor)
      segundo_maior = max(numeros)
      return segundo_maior


### 5. Crie uma função que receba uma lista de tuplas, cada uma contendo o nome e a idade de uma pessoa, e retorne a lista ordenada pelo nome das pessoas em ordem alfabética.

def ordenar_por_nome(pessoas):
  if not pessoas:
    return []
  
  pessoas.sort(key=lambda pessoa: pessoa[0].upper())
  return pessoas

### 6. Observe os espaços sublinhados e complete o código.

```
  import __________.pyplot as plt

  import numpy as ___

  fig, axs = plt.subplots(ncols=2, nrows=2, figsize=(5.5, 3.5), layout="constrained")

  for ___ in range(2):

    for ___ in range(2):

      axs[row, col].annotate(f'axs[{row}, {col}]', (0.5, 0.5), transform=axs[row, col].transAxes, ha='center', va='center', ________=18, color='darkgrey')

  fig.suptitle('__.subplots()')
```

    import matplotlib.pyplot as plt
    import numpy as np

    fig, axs = plt.subplots(ncols=2, nrows=2, figsize=(5.5, 3.5), layout="constrained")

    for row in range(2):
        for col in range(2):
            axs[row, col].annotate(f'axs[{row}, {col}]', (0.5, 0.5), transform=axs[row, col].transAxes, ha='center', va='center', size=18, color='darkgrey')

    fig.suptitle('plt.subplots()')

### 7. Observe os espaços sublinhados e complete o código.

```
    import numpy as np

    import __________ as mpl

    import __________.______ as plt

    x = np.________(-2 * np.pi, 2 * np.pi, 100)

    y = np.____(x)

    __, __ = plt.subplots()

    ax.____(_, _)
```

    import numpy as np
    import matplotlib as mpl
    import matplotlib.pyplot as plt

    x = np.linspace(-2 * np.pi, 2 * np.pi, 100)
    y = np.sin(x)
    fig, ax = plt.subplots()
    ax.plot(x, y)

### 8. Utilizando pandas, como realizar a leitura de um arquivo CSV em um DataFrame e exibir as primeiras linhas?

    import pandas as pd
    dados = pd.read_csv('arquivo.csv')
    print(dados.head())

### 9. Utilizando pandas, como selecionar uma coluna específica e filtrar linhas em um “DataFrame” com base em uma condição?

    ...
    df_filtrado = df[df['Idade'] >= 30]
    print(df_filtrado)
    
### 10. Utilizando pandas, como lidar com valores ausentes (NaN) em um DataFrame?

#### - Apagar as linha que tenham valore ausentes

    data.dropna(inplace=True)

#### - Preencher com uma constante

    data['Idade'].fillna(0, inplace=True)

#### - Preenchar com um valor calculado( interpolação linear, média, mediana)

    data['column_name'].interpolate('linear', inplace=True)



    

