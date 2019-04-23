# UnicodeCSV

A wrapper of Python2's csv module to handle UTF-8 csv files, originally implemented in https://docs.python.org/2.7/library/csv.html. 

## Installation (Jython of Fiji / ImageJ)

1. Place this directory under `Fiji.app/jars/Lib` 

## Usage

```python
from __future__ import print_function, with_statement
import codecs

from UnicodeCSV import UnicodeCSV as ucsv

data = []
with codecs.open("filename.csv", "r", "utf-8") as f:
    reader = ucsv.UnicodeReader(f)
    for row in reader:
      data.append(row)
      print(", ".join(row))

with codecs.open("filename.csv", "w", "utf-8") as f:
    writer = ucsv.UnicodeWriter(f)
    writer.writerows(data)

```
