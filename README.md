# reto-7-hasta-reto-15-
.py
from itertools import combinations_with_replacement

string, k = input().split()
k = int(k)

string_sorted = sorted(string)

for combo in combinations_with_replacement(string_sorted, k):
    print("".join(combo))

reto= #8
from itertools import groupby

s = input()

for key, group in groupby(s):
    print((len(list(group)), int(key)), end=" ")
   
  reto = #9
  from itertools import combinations

n = int(input())
letters = input().split()
k = int(input())

all_combinations = list(combinations(letters, k))

count = 0

for combination in all_combinations:
    if 'a' in combination:
        count += 1

print(count / len(all_combinations))

reto = #10
from itertools import product

k, m = map(int, input().split())

lists = []
for _ in range(k):
    
    data = list(map(int, input().split()))[1:]
    lists.append(data)

max_val = 0

for combination in product(*lists):
    
    current_val = sum(x**2 for x in combination) % m
    if current_val > max_val:
        max_val = current_val

print(max_val)

reto = #11
#!/bin/python3

#!/bin/bin/python3

import math
import os
import random
import re
import sys

first_multiple_input = input().rstrip().split()

n = int(first_multiple_input[0])
m = int(first_multiple_input[1])

matrix = []

for _ in range(n):
    matrix_item = input()
    matrix.append(matrix_item)

decoded_string = "".join([matrix[row][col] for col in range(m) for row in range(n)])

clean_string = re.sub(r'(?<=\w)[^\w]+(?=\w)', ' ', decoded_string)

print(clean_string)

 reto= # 12

 from html.parser import HTMLParser

class MyHTMLParser(HTMLParser):
    def handle_comment(self, data):
        # Si el comentario contiene salto de línea, es multilínea
        if '\n' in data:
            print(">>> Multi-line Comment")
        else:
            print(">>> Single-line Comment")
        print(data)

    def handle_data(self, data):
        # Ignoramos si la data es simplemente un salto de línea
        if data != '\n':
            print(">>> Data")
            print(data)

# Lectura de las N líneas de entrada HTML
html = ""
for _ in range(int(input())):
    html += input() + '\n'

# Instanciamos el parser y procesamos el HTML
parser = MyHTMLParser()
parser.feed(html)
parser.close()

reto = #13
from html.parser import HTMLParser

class MyHTMLParser(HTMLParser):
    def handle_starttag(self, tag, attrs):
        print(tag)
        for attr, value in attrs:
            print(f"-> {attr} > {value}")

    def handle_startendtag(self, tag, attrs):
        print(tag)
        for attr, value in attrs:
            print(f"-> {attr} > {value}")

html = ""
for _ in range(int(input())):
    html += input() + '\n'

parser = MyHTMLParser()
parser.feed(html)

reto= # 14

import re

for _ in range(int(input())):
    uid = input().strip()
    
    cond_length = len(uid) == 10
    
    cond_alnum = uid.isalnum()
    
    cond_no_repeat = len(set(uid)) == 10
    
    cond_upper = len(re.findall(r'[A-Z]', uid)) >= 2
    
    cond_digits = len(re.findall(r'[0-9]', uid)) >= 3
    
    if cond_length and cond_alnum and cond_no_repeat and cond_upper and cond_digits:
        print('Valid')
    else:
        print('Invalid')


      reto= #15
      import re

def validate_credit_cards():

    structure_regex = r'^[456](\d{15}|\d{3}(-\d{4}){3})$'

    consecutive_regex = r'(\d)\1{3,}'
    
    n = int(input().strip())
    
    for _ in range(n):
        card = input().strip()
        
        if re.match(structure_regex, card):

            clean_card = card.replace('-', '')
            
            if re.search(consecutive_regex, clean_card):
                print("Invalid")
            else:
                print("Valid")
        else:
            print("Invalid")

if __name__ == '__main__':
    validate_credit_cards()
