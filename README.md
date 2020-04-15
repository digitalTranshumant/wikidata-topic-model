# Generating topic for Wikidata Items that have Wikipedia article (sitelinks)

This is an off-line implementation of the [Wikidata Topic Model API](https://github.com/geohci/wikidata-topic-model-api). The aim is to compute the topics for all the Wikidata Items that has an article in any Wikipedia. 

These notebooks makes usage of the [WMF's Hadoop Cluster](https://wikitech.wikimedia.org/wiki/Analytics/Systems/Cluster). If you don't have access to that cluster, you will need to rewrite the code using the [Wikidata Dump](https://dumps.wikimedia.org/wikidata). 

Here we use two tables from the [Wikimedia Data Lake](https://wikitech.wikimedia.org/wiki/Analytics/Data_Lake):

* [wmf.wikidata_item_page_link](https://wikitech.wikimedia.org/wiki/Analytics/Data_Lake/Edits/Wikidata_item_page_link): Containig the relation between Wikidata Items and Page Titles. This is results are equivalent to the 'sitelinks' value that you will find in the Wikidata Dump.

* [wmf.wikidata_entity](https://wikitech.wikimedia.org/wiki/Analytics/Data_Lake/Edits/Wikidata_entity): From we exract the claims for each Wikidata Items. You will find equilivant information in the claims field of Wikidata dump. 

This code works is based on the  [wikidata-topic-model-api](https://github.com/geohci/wikidata-topic-model-api). If want to get the topic for sinlge (or small set of) Wikidata Item(s), we recommend you to use this experimental API: https://tools.wmflabs.org/wiki-topic/