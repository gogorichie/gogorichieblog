---
title: "How to find duplicate rows in SQL Server"
date: 2008-06-10
draft: false
summary: ""
summaryImage: ""
tags: ["SQL"]
---


I ran into this problem the other day at work with duplicate rows while trying to merge data from two separate tables into the same table. I couldn't remember so I just ran a quick search using [Google](http://www.google.com/search?hl=en&q=duplicate+records+in+sql) and came across the solution on a [Microsoft knowledge base](http://support.microsoft.com/kb/139444) page.

<pre>-------------------------------------------------------</pre>

<pre>**_The first step is to identify which rows have duplicate primary key
values:_**</pre>

<pre>SELECT col1, col2, count(*)FROM t1GROUP BY col1, col2HAVING count(*) > 1</pre>

<pre>**_This will return one row for each set of duplicate PK values
in the table. The last column in this result is the number of
duplicates for the particular PK value._**</pre>

col1               col2

1                   1                   2

---------------------------------------------------------------