# csv_parsing

A basic CSV parser written in Python in less than a day for fun and learning purposes. Originally written for another project.

Obviously not recommended for use in any serious capacity.

## Usage

To use the parser, you can follow the example below:

```py
from .parsing.parser import CsvParser, BadLineMode

file = open("csv_file.csv", encoding="utf-8")

parser = CsvParser(
    file,
    BadLineMode.ERROR,
    print_error_to=None,
    allow_multiline_strings=True,
)

# parse() is a generator that parses a line and returns a CsvRow per iteration
for row in parser.parse():
    # returns a CsvRow
    value = row.get_value("column_name")

    # Extracts string value from CsvRow
    value_string = value.get_value()
```
