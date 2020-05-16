# HSCW09

Historical Snapshots ClueWeb09 - this dataset was created from a subset of ClueWeb09 documents, it contains the historical snapshots from 2008, of a set of documents initially retreived for each of the 1-200 titles of topics from TREC's ClueWeb09 dataset that served as queries. 

The historiacl snapshots were retreived using the WayBack Machine of the Internet Archive (https://archive.org/web/).

# HSCW09 Dataset

The snapshots were distributed among 12 month-long intervals in 2008, in each interval there is only one snapshot per document.
In the dataset file (HSCW09.zip) there are 12 folders, each folder contains the data for a specific interval. 
The interval named 2008-01-01 contains the snapshots of the documents, that had an available snapshot in January 2008, 2008-02-01 contains snapshots from February 2008, 2008-03-01 contains snapshots from March 2008 and so on.

Each intervals' files are stored in warc format and ready to be indexed using the Lamour Indri toolkit, to use the data:

- Unzip the HSCW09.zip file.
- Index each intervals' inner folder (the folders named 2008-01-01, 2008-02-01 and so on) separatly, using the Indri toolkit.

# Queries 

We used the ClueWeb09 queries that can be downloaded here: http://trec.nist.gov/data/webmain.html.
The mapping between each document ID to the query number that it was initially retreived for, can be found in the document_query_mapping.tsv file. 
