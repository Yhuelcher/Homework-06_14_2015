
BASIC LEVEL
PART 1: Read in the data with csv.reader() and store it in a list of lists called 'data'.
Hint: This is a TSV file, and csv.reader() needs to be told how to handle it.

```import csv
with open('chipotle.tsv', 'rU') as f:
    data =[row for row in csv.reader(f, delimiter='\t')]``` 
    

BASIC LEVEL
PART 2: Separate the header and data into two different lists.

```header = data [0:1]```

```data = data [1:]```

```data```

INTERMEDIATE LEVEL
PART 3: Calculate the average price of an order.
Hint: Examine the data to see if the 'quantity' column is relevant to this calculation.
Hint: Think carefully about the simplest way to do this!

amount = []
for row in data:
    a = row[4] 
    b = float(a.replace('$',''))
    amount.append(b)
    x = sum(amount)

total = sum([float(row[-1].replace('$','')) for row in data])
number_of_orders =len(set([row[0] for row in data]))

avg=round(float(total) / float(number_of_orders),2)


INTERMEDIATE LEVEL
PART 4: Create a list (or set) of all unique sodas and soft drinks that they sell.
Note: Just look for 'Canned Soda' and 'Canned Soft Drink', and ignore other drinks like 'Izze'.

set([row[3] for row in data if row[2]=='Canned Soda' or row[2]=='Canned Soft Drink'])




