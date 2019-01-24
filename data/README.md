## croci_types.csv
The number of citations for the different DOI categories. We have classified the DOI resources into five classes: Journal, Book, Proceedings, Dataset, Other. 
The citations count are taken from two different sources: 
1) COCI: those are open citations made available and retrieved from the COCI dataset. In this case the citations are counted through the analysis of all the DOIs (items in the dataset) that have an open reference-list.
2) Crossref: the number of citations given by Crossref. In this case the total count includes also citations made from closed resources which do not publish there reference list: closed citations. This value is presented as an attribute for each item in the COCI dataset.
### Columns:
*type*: the type of DOI: Journal, Book, Proceedings, Dataset, Other.  
*label*: the label value.  
*coci_open_cit*: the citation count using the first source previously described.  
*crossref_close_cit*: the citation count using the second source previously described.

**Note:** All the information are included/calculated from the last COCI dataset dump available at the OpenCitations website:
http://opencitations.net/download#coci      

## publishers_cits.csv
Taken in consideration the same previous sources as citation count values. In this file this count is calculated for each different publisher.
### Columns:
*publisher*: the name of the publisher.  
*doi_prefix*: the list of DOI prefixes used by that publisher.  
*coci_open_cit*: the citation count using the first source previously described.  
*crossref_close_cit*: the citation count using the second source previously described.  
*total_cit*: the total number of citations (*coci_open_cit* + *crossref_close_cit*).  

**Note:** All the information are included/calculated from the last COCI dataset dump available at the OpenCitations website:
http://opencitations.net/download#coci 

## 20publishers_cr.csv
This file contains the number of: open,limited, and closed, DOI resources having a reference list inside Crossref.
To retrieve such data we used the Crossref API. For instance, the following call retrieves the number of 'closed' items having a reference list and 'Elsevir' as publisher.   
http://api.crossref.org/members/78/works?filter=has-references:true,reference-visibility:closed  
We took the 20 publishers having the higher number of open citations in COCI, using the previous **publishers_cits.csv**
### Columns:
*publisher*: the name of the publisher.  
*open*: the number of items in crossref with an 'open' visibility for there reference list.  
*limited*: the number of items in crossref with a 'limited' visibility for there reference list.  
*closed*: the number of items in crossref with a 'closed' visibility for there reference list.  
