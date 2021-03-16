import csv
import os
import pandas as pd
from pathlib import Path
from os import listdir
from os.path import isfile, join
import numpy as np
import matplotlib.pyplot as plt
from tqdm.notebook import trange, tqdm
from time import sleep

origin_file_path = 'numword.csv'
file_path = r'C:\Users\TaeFreeze\Documents\thaijofiles\health01'
file_remove_path = r'C:\Users\TaeFreeze\Documents\thaijofiles\health01/'

dup = []
with open('numword.csv') as csvfile:
    reader = csv.reader(csvfile)
    for row in reader:
        dup.append(row[0])
        
#print(dup)
        
lenght = len(dup)
print('origin file count = ' + str(lenght) + ' files')

file_count = os.listdir(file_path)

#print(file_count)


source_file_lenght = len(file_count)
print('file count = ' + str(source_file_lenght) + ' files')

file_not_dup = list(set(file_count) - set(dup))

#print(file_not_dup)

file_not_dup_lenght = len(file_not_dup)
print('file thats not duplicate with origin count = ' + str(file_not_dup_lenght) + ' files')

count = [lenght,source_file_lenght,file_not_dup_lenght]
name = ('dup', 'file_count', 'file_not_dup')
y_pos = np.arange(len(name))

# Create bars
plt.bar(y_pos, count)

# Create names on the x-axis
plt.xticks(y_pos, name)

# Show graphic
plt.show()

try:
    for filenameRM in tqdm(file_count,desc='Delete Progress'):
        if filenameRM in dup:
            os.remove(file_remove_path + filenameRM)
except FileNotFoundError as error:
    print(error)
