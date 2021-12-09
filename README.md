# SPARQL Anything resources

This repository collects links and resources for the class on SPARQL Anything that will take place on December 16th in the context of the [Knowledge Engineering course](https://www.unibo.it/it/didattica/insegnamenti/insegnamento/2021/446613).

## Video Tutorial and Slides

## SPARQL Anything documentation

## Homework

Goal: Design a SPARQL Anything construct query that extracts the following [target Knowledge Graph](https://raw.githubusercontent.com/luigi-asprino/knowledge-engineering/master/target_kg.ttl) from [this input file](https://raw.githubusercontent.com/luigi-asprino/knowledge-engineering/master/COLLEZIONE_GAM.json).

### Target Knowledge

```turtle
@prefix arco:  <https://w3id.org/arco/ontology/arco/> .
@prefix ex:    <http://example.org/> .
@prefix rdf:   <http://www.w3.org/2000/01/rdf-schema#> .
@prefix rdfs:  <http://www.w3.org/2000/01/rdf-schema#> .
@prefix arco-cd: <https://w3id.org/arco/ontology/context-description/> .

ex:Autoritratto_a_28_anni_by_MORELLI_Domenico
        a          arco:CulturalProperty ;
        rdf:label  "Autoritratto a 28 anni" .

ex:Autoritratto_a_16_anni_by_MORELLI_Domenico
        a          arco:CulturalProperty ;
        rdf:label  "Autoritratto a 16 anni" .

ex:Authorship_attribution_MORELLI_Domenico_Autoritratto_a_28_anni
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  ex:MORELLI_Domenico ;
        arco-cd:isAuthorshipAttributionOf
                ex:Autoritratto_a_28_anni_by_MORELLI_Domenico .

ex:Authorship_attribution_MORELLI_Domenico_Autoritratto_a_16_anni
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  ex:MORELLI_Domenico ;
        arco-cd:isAuthorshipAttributionOf
                ex:Autoritratto_a_16_anni_by_MORELLI_Domenico .

ex:MORELLI_Domenico  rdf:label  "MORELLI Domenico" .
```

### Input

```json
[
  {
    "Autore":"MORELLI Domenico",
    "Titolo":"Autoritratto a 16 anni",
    "Datazione":"1839",
    "Tecnica":"matita su carta seppia",
    "Dimensioni":"mm 131(h) x 95(b)",
    "Immagine":"http://93.62.170.226/foto/gam/Morelli/Leg1-01.jpg"
  },
  {
    "Autore":"MORELLI Domenico",
    "Titolo":"Autoritratto a 28 anni",
    "Datazione":"1851",
    "Tecnica":"matita e acquerello su cartoncino",
    "Dimensioni":"mm 216(h) x 178(b)",
    "Immagine":"http://93.62.170.226/foto/gam/Morelli/Leg1-02.jpg"
  }
]

```
