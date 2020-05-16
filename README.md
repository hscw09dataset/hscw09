# HSCW09

Our first goal was to create a dataset that allows to study the temporal
dynamics of documents that are highly ranked for queries. To this end,
we used TREC's ClueWeb09 dataset \cite{ClueWeb09}. The titles of
topics $1$-$200$ served as queries. Krovetz stemming was applied to
queries and documents.
We applied standard
language-model-based retrieval for each query. Specifically, we used
the KL divergence between the unsmoothed maximum likelihood estimate
induced from the query and the Dirichlet smoothed document language models for
ranking; the smoothing parameter was set to $1000$
\cite{Lafferty+Zhai:01a}. We scanned each retrieved list top down and
removed documents whose Waterloo's spam score \cite{Waterloo10} was
below $50$ until we have accumulated $50$ documents. We use $L^{0}_{\query}$ to denote the retrieved list for query $\query$; $0$ is the timestamp. The set of all documents in the lists retrieved for the $200$ queries is referred to as the {\em base set}; it contains $9986$ different documents. (Some documents are among the top-retrieved for more than one query.)

The next step was to collect past versions of the documents in
$L^{\query}_{0}$ for each query $\query$. To that end, we used the
WayBack Machine of the Internet Archive
(\url{https://archive.org/web/}). The Internet Archive is a large
repository of Web pages crawlled in different points in time. Since
ClueWeb09 is a crawl from 2009, we used past versions from
2008. Specifically, we used $12$ time intervals, each corresponds to a
calendar month in 2008. We used a document's
{\em earliest} snapshot in an interval as its version for the interval in case a snapshot
existed. Thus, we consider at most $13$ versions of a document: the
ClueWeb version (\# 0) and the 12 past versions from 2008. The 2008
document lists for query $\query$ are denoted $L^{\query}_{-1},
\ldots, L^{\query}_{-12}$ where $-1$ corresponds to the December
interval and $-12$ corresponds to the January interval. Each of these lists contains at most $50$ documents depending on the number of documents from $L^{\query}_{0}$ with at least one past snapshot in the corresponding interval. In what follows, we use $\doc^{\query}_{i}$ where $i \in \{0,-1,\ldots,-12\}$ to denote a document in list $L^{\query}_{i}$.
