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
 
--------------------------------------------------------------------------------------
### STEP 2
--------------------------------------------------------------------------------------
create collections in arangodb with these given names and load the data in JSON format.

`WikiItems` - items collection containing item labels, descriptions and claims.

`WikiProps` - property collection containing property labels and descriptions.

`WikiEdge` - edge collection containing edges between items and properties. (_from : items , _to : properties)

`WikiClaims` - claim collection containing property keys with labels.
