# Scraping Books

## Overview
I scraped https://books.toscrape.com/ using `requests` and `BeautifulSoup`.
For every category in the left menu, the code opens the category page and collects the books on it.
The result is **517 books** saved in `books.csv`.

## Columns
Category, Name, Price, In_Stock

## Problems and how I solved them
| Problem | Solution |
|---|---|
| The price came with a strange character before the pound sign | removed it with `replace()` |
| Some data may be missing | filled with `Unknown` |
| The category is not shown on the books list page | took it from the category pages in the left menu |

## Note
The code reads the first page of each category only.
