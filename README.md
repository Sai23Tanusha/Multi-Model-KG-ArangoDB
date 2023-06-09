## Problem Set 1 - `Sai Tanusha` `(Tech Pirates)`
## Multi-Model Database Knowledge Graphs Using ArangoDB with Wikidata 
-------------------------------------------------------------------------------------

Problem Statement 1: Load the Wikidata into ArangoDB and create a graph that represents the relationships between entities, such as people, places, and things. Use AQL to query the graph and find all instances of a particular entity type, such as all instances of a person.

-------------------------------------------------------------------------------------

Wikidata is a free, multilingual knowledge graph that contains structured data on a vast array of topics, ranging from people and organizations to locations and events. 
Processing Wikidata dumps is just like any ETL job: `Extract` `Transform` `Load`

--------------------------------------------------------------------------------------
### STEP 1
--------------------------------------------------------------------------------------
qwikidata is a Python package with tools that allow you to interact with Wikidata.
The package defines a set of classes that allow you to represent Wikidata entities in a Pythonic way. It also provides a Pythonic way to access three data sources,
   1) linked data interface
   2) sparql query service   ---------- (IMPLEMENTED)
   3) json dump   ---------- (IMPLEMENTED)
 
```diff
@@ refer : Wikidata-Extraction-SPARQL.rst @@
```
- to implement 2) i have used `Wikidata Query Service` and have formed 2 collections Items and Props. Was finiding it difficult to form a edge collection.

```diff
@@ refer : Wikidata-Extraction.ipynb @@
```
- i have implemented 3) using `qwikidata` and `pyarango` and have formed all the collections mentioned in step 2.
 
--------------------------------------------------------------------------------------
### STEP 2
--------------------------------------------------------------------------------------
create collections in arangodb with these given names and load the data in JSON format.

`WikiItems` - items collection containing item labels, descriptions and claims.

`WikiProps` - property collection containing property labels and descriptions.

`WikiEdge` - edge collection containing edges between items and properties. (_from : WikiItems , _to : WikiProps)

`WikiClaims` - claim collection containing property keys with labels.
- also can be said as ___VIEWS___
```diff 
@@ (refer " WikiClaims-Queries" ) @@ 
```
--------------------------------------------------------------------------------------
### STEP 3
--------------------------------------------------------------------------------------
create a graph where we input edge collection, _from and _to. 
```diff 
@@ (refer "SAI TANUSHA (tech pirates).pptx" ) for graph images @@ 
```
--------------------------------------------------------------------------------------
### STEP 4
--------------------------------------------------------------------------------------
Formed 2 Questions and performed AQL queries based on that.
```diff 
@@ (refer " Questions-Queries" ) @@ 
```
- Q 1.  Find the instances of all the items collectively and extract the result in the form of json file. 
```diff
@@ results-_system.csv @@
```
- Q 2. Using 3 Edge collections and with a minimum of 2 hops and a max of 3 hops between the airports find the path in the form of a graph.
```diff
@@ result-graph.jpg @@
```
