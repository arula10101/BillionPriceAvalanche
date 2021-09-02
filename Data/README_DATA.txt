***************************************************
*Data for paper titled "Scraped Data and Sticky Prices", published in the Review of Economics and Statistics
*Author: Alberto Cavallo
*Date: 7/2016
**************************************************

INSTRUCTIONS

-This dataverse contains the raw data. For STATA scripts and other replication materials, visit the Review of Economics and Statistics Dataverse.
https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi%3A10.7910%2FDVN%2F021GV6

DATA DICTIONARY

-The raw data files are in Stata 14 and Excel formats. 

-Each database is named after the country to which it belongs. In the case of the US, the file named "usa_all" contains the pooled data from 4 retailers. Data from each retailer is also separately provided and named "usa1", "usa2", etc. 

-"usa1" is a supermarket. Contains 9 million daily observations collected from 05/2008 to 07/2010 for 24 thousand products in 26 COICOP categories. 
-"usa2" is a department store/supermarket. Contains 10 million daily observations collected from 03/2008 to 07/2010 for 94 thousand products in 33 COICOP categories. 
-"usa3" is a drugstore/convenience store. Contains 4 million daily observations collected from 03/2009 to 07/2010 for 22 thousand products in 34 COICOP categories. 
-"usa4" is a Electronics retailer. Contains 5 million daily observations collected from 03/2008 to 07/2010 for 30 thousand products in 19 COICOP categories. 
-"argentina" is a supermarket. Contains 11 million daily observations collected from 10/2007 to 08/2010 for 28 thousand products in 74 categories. 
-"brazil" is a supermarket. Contains 10 million daily observations collected from 10/2007 to 08/2010 for 22 thousand products in 72 categories. 
-"chile" is a supermarket. Contains 10 million daily observations collected from 10/2007 to 08/2010 for 24 thousand products in 72 categories. 
-" colombia" is a supermarket. Contains 4 million daily observations collected from 11/2007 to 08/2010 for 9 thousand products in 59 categories. 


-All databases contain roughly the same variables. Please see below with a description of each variable:

---------------------------------------------------------------------------------------------------
              storage   display    value
variable name   type    format     label      variable label
---------------------------------------------------------------------------------------------------
rid_id          long    %12.0g    Unique numeric id that identifies a single product in a given retailer            
cat_url         float   %9.0g     Unique numeric id that identifies a unique url (web address) in which the product was found. It can be used as a narrow category definition.              
bppcat          int     %12.0g    Unique numerid id that identifies a unique category for each product. It can be used a broad category definition. In the case of the US, it corresponds to the COICOP classification.      
date            float   %td       Date when the price was collected, in Stata format.            
miss            float   %9.0g     Equal to 1 if the price was missing in the original data and has been carried forward (see details in the paper)          
price0          double  %10.0g    Original "raw" price data. It is missing when miss=1           
price           float   %9.0g     Same as price0.            
nsprice         float   %9.0g     Same as price, but prices identified as sales (using the v-shaped sale algorithm described in the paper) have been set to missing.            
sale            float   %9.0g     Sale indicator, equal to 1 if this price has been identified as sales using the v-shaped sale algorithm described in the paper         
fullprice       float   %9.0g     Main price variable used in the paper. It is the original price variable with missing prices carried forward (up to 5 months, as described in the paper)           
nsfullprice     float   %9.0g     Same as fullprice, but excluding sale prices. Used nsprice for carry forward missing prices.             
fullsale        float   %9.0g     Sale indicator, based on "sale" variable, with sale carried forward for dates of missing prices.             
initialspell    float   %9.0g     Equal to 1 if this is the first price spell for a given product.           
lastspell       float   %9.0g     Equal to 1 if this is the last price spell for a given product.           
category        float   %9.0g     Main category variable used in the paper. Same as bppcat.             
retailer        str4    %9s       Unique string id that identifies a retailer ("usa1", "usa2", etc)            
id              float   %9.0g     Main product id variable used in the paper. It is created using "group(id retailer)", so that it provides a unique numeric id for each product-retailer combination. 
---------------------------------------------------------------------------------------------------

