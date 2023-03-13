# SWDE-Dataset
Mirror for SWDE dataset

# Paper
[From One Tree to a Forest: a Unified Solution forStructured Web Data Extraction](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/StructedDataExtraction_SIGIR2011.pdf)

# Motivation

This dataset is a real-world web page collection used for research on the automatic extraction of structured data (e.g., attribute-value pairs of entities) from the Web. We hope it could serve as a useful benchmark for evaluating and comparing different methods for structured web data extraction.
Contents of the Dataset

# Contents of the dataset

- 8 verticals with diverse semantics;
- 80 web sites (10 per vertical);
- 124,291 web pages (200 ~ 2,000 per web site), each containing a single data record with detailed information of an entity;
- 32 attributes (3 ~ 5 per vertical) associated with carefully labeled ground-truth of corresponding values in each web page.

The goal of structured data extraction is to automatically identify the values of these attributes from web pages.
The involved verticals are summarized as follows:


| Vertical   | #Sites | #Pages | #Attributes | Attributes                                          |
|------------|--------|--------|-------------|-----------------------------------------------------|
| Auto       | 10     | 17,923 | 4           | model, price, engine, fuel_economy                  |
| Book       | 10     | 20,000 | 5           | title, author, isbn_13, publisher, publication_date |
| Camera     | 10     | 5,258  | 3           | model, price, manufacturer                          |
| Job        | 10     | 20,000 | 4           | title, company, location, date_posted               |
| Movie      | 10     | 20,000 | 4           | title, director, genre, mpaa_rating                 |
| NBA Player | 10     | 4,405  | 4           | name, team, height, weight                          |
| Restaurant | 10     | 20,000 | 4           | name, address, phone, cuisine                       |
| University | 10     | 16,705 | 4           | name, phone, website, type                          |


# Format of Web Pages

Each web page in the dataset is stored as one .htm file (in UTF-8 encoding) where the first tag encodes the source URL of the page.
Format of Ground-truth Files

For each web site, the page-level ground-truth of attribute values has been labeled using handcrafted regular expressions and stored in .txt files (in UTF-8 encoding) named as: "<vertical>-<site>-<attribute>.txt".
In each such file:

The first line stores the names of vertical, site, and attribute, separated by TAB characters ('\t').

The second line stores some statistics (separated by TABs) w.r.t. the corresponding site and attribute, including:

- the total number of pages,
- the number of pages containing attribute values,
- the total number of attribute values contained in the pages,
- the number of unique attribute values.

Each remaining line stores the ground-truth information (separated by TABs) of one page, in sequence of: *page ID, *the number of attribute values in the page, *attribute values ("<NULL>" in case of non-existence).

# Notes on Ground-truth Labeling

The ground-truth labeling was conducted in the DOM-node level. More specifically, the candidate attribute values in a web page are the non-empty strings contained in text nodes in the corresponding DOM tree. One page (although containing a single data record) may contain multiple distinct values that correspond to an attribute (e.g., multiple authors of a book, multiple granularity levels of addresses). Currently, when a text node presents a mixture of multiple attributes, its string value is labeled with each of these attributes, if no substitute is available. Before being stored in .txt files, the raw attribute values were refined by removing redundant separators (e.g., ' ', '\t', '\n').
Reference

The authors would appreciate it if you cite the following paper when using the dataset:
```
Qiang Hao, Rui Cai, Yanwei Pang, and Lei Zhang. "From One Tree to a Forest: a Uniﬁed Solution for Structured Web Data Extraction". in Proc. of the 34th International ACM SIGIR Conference on Research and Development in Information Retrieval (SIGIR 2011), pp.775-784, Beijing, China. July 24-28, 2011.
```

# Notes
Year: 2011
URL: https://swde.codeplex.com/
License: No license specified, the work may be protected by copyright.
