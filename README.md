Solr Elevate Example
====================

A minimal ready to use Solr distribution that contains the Solr Elevate Plugin along with a sample configuration. 


### Blog Article
A blog article introducing this plugin can be found [here](https://medium.com/@kaismh/automated-solution-for-query-elevation-using-solr-a15ce88b2762).

### Solr Plugin
The Solr plugin can be found [here](https://github.com/kaismh/solr-elevate-creator).        

## Usage Guide
### Deployment
* git clone <https://github.com/kaismh/solr-elevate-example>
* Import products.sql found inside data folder into MySQL
* Change server/solr/products/conf/dataimport.properties and elevate-creator.properties to match your DB settings 
* cd solr-elevate-example
* bin/solr start

### Usage

To see elevation in action issue the following request:

```
http://localhost:8983/solr/products/elevate?q=linux
``` 
To view the result for same query but without elevation issue the following:

```
http://localhost:8983/solr/products/elevate?q=linux&enableElevation=false
``` 
### Plugin
To see plugin in action perform the following:

* Update elevation\_query\_text in the database
* Start the DIH indexing by issuing the following:

```
http://localhost:8983/solr/products/dataimport?command=full-import
``` 

* Check server/solr/products/data/**elevate.xml** for the changes and issue relevant elevate requests  


## Dataset
The dataset used it this example is based on [Amazon E-commerce Products](http://dbs.uni-leipzig.de/en/research/projects/object_matching/fever/benchmark_datasets_for_entity_resolution)

## License & Author
 
Solr Elevate Example is licensed under [Apache License 2.0] (http://www.apache.org/licenses/LICENSE-2.0.html). For license terms, see LICENSE.txt.

#### Created by Kais Hassan
