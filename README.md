## About This Repository
This repository contains a python3 script used to write structured data on Wikimedia Commons (SDC). 

### Additional Reading:
* The underlying structure is based on this [blog post](https://byabbe.se/2020/09/15/writing-structured-data-on-commons-with-python) by Albin Larsson.

## Requirements

To run it you will have to install dependencies using:
`pip install -r requirements.txt`

## User Account

When running the script, you will be asked to login using a Wikimedia Commons account.

## Data

Data is read from the a CSV file:

````
python3 app.py --data data.csv
````

| Filename      |Caption\|sv            |Caption\|en       |P180 |P217\|P195              |
| --------------|-----------------------|------------------|-----|------------------------|
| Test.pdf      | beskrivning på svenska|caption in english|Q147 |NMA.0096620-03\|Q1142142|

This will add the following statements:
* Caption _beskrivning på svenska_ in **Swedish**
* Catpion _caption in english_ in **English**
* [Depicts](https://www.wikidata.org/wiki/Property:P180) → [kitten](https://www.wikidata.org/wiki/Q147)
* [Inventory number](https://www.wikidata.org/wiki/Property:P217) → NMA.0096620-03
* * With qualifier [Collection](https://www.wikidata.org/wiki/Property:P195) → [Nordic Museum](https://www.wikidata.org/wiki/Q1142142)