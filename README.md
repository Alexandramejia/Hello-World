# Hello-World
import matplotlib.pyplot as plt
import pandas as pd

pop = pd.read_csv('covidCases.csv')

borough = input('Enter borough name: ')
output = input('Enter output name: ')
print('Min: ', pop[borough].min())
print('Max: ', pop[borough].max())
print('Mean: ', pop[borough].mean())
print('Median: ', pop[borough].median())
print('Standard Deviation: ', pop[borough].std())

pop['Fraction'] = pop[borough]/pop['Case Count']
pop.plot(x = 'Date of interest', y = 'Fraction')

fig = plt.gcf()
fig.savefig(output)
