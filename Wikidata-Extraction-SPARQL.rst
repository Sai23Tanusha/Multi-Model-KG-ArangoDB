* ``properties`` - SPARQL query for all properties

.. code-block:: python

SELECT ?property ?propertyType ?propertyLabel ?propertyDescription ?propertyAltLabel WHERE {
  ?property wikibase:propertyType ?propertyType .
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
ORDER BY ASC(xsd:integer(STRAFTER(STR(?property), 'P')))


* ``items`` - SPARQL query for items having a particular property

.. code-block:: python

SELECT ?item ?itemLabel ?value ?valueLabel WHERE {
  ?item wdt:P1800 ?value  # can change to any 'P_' property number     
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
