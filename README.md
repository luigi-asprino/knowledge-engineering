# SPARQL Anything resources

This repository collects links and resources for the class on SPARQL Anything that will take place on December 16th in the context of the [Knowledge Engineering course](https://www.unibo.it/it/didattica/insegnamenti/insegnamento/2021/446613).

## Video Tutorial and Slides

## SPARQL Anything links

-  [Website](https://sparql-anything.cc/)
-  [Documentation](https://sparql-anything.readthedocs.io/en/latest/)
-  [GitHub Repository](https://github.com/SPARQL-Anything/sparql.anything)
-  [Releases](https://github.com/SPARQL-Anything/sparql.anything/releases)
-  [Showcase IMMA](https://github.com/SPARQL-Anything/showcase-imma) [Showcase Propbank](https://github.com/SPARQL-Anything/showcase-propbank) [Showcase Tate Gallery](https://github.com/SPARQL-Anything/showcase-tate)

## Assignment 1

Goal: Designing a SPARQL Anything construct query that extracts the following [target Knowledge Graph](https://raw.githubusercontent.com/luigi-asprino/knowledge-engineering/master/target_kg.ttl) from [this input file](https://raw.githubusercontent.com/luigi-asprino/knowledge-engineering/master/COLLEZIONE_GAM.json).

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

## Assignment 2

Goal: Designing a SPARQL Anything construct query that extracts the following [target Knowledge Graph](https://raw.githubusercontent.com/luigi-asprino/knowledge-engineering/master/target_kg_2.ttl) from [this input file](https://raw.githubusercontent.com/luigi-asprino/knowledge-engineering/master/csv_input.csv).


### Target Knowledge Graph

```turtle
@prefix schema: <http://schema.org/> .
@prefix ex:    <http://example.org/> .
@prefix rdf:   <http://www.w3.org/2000/01/rdf-schema#> .
@prefix rdfs:  <http://www.w3.org/2000/01/rdf-schema#> .

ex:You_Shook_Me_All_Night_Long
        a                schema:MusicRecording ;
        schema:byArtist  ex:ACDC ;
        schema:name      "You Shook Me All Night Long" .

ex:Muse  a           schema:MusicGroup ;
        schema:name  "Muse" .

ex:The_Beatles  a    schema:MusicGroup ;
        schema:name  "The Beatles" .

ex:Seven_Nation_Army  a  schema:MusicRecording ;
        schema:byArtist  ex:The_White_Stripes ;
        schema:name      "Seven Nation Army" .

ex:Come_Together  a      schema:MusicRecording ;
        schema:byArtist  ex:The_Beatles ;
        schema:name      "Come Together" .

ex:Thunderstruck  a      schema:MusicRecording ;
        schema:byArtist  ex:ACDC ;
        schema:name      "Thunderstruck" .

ex:ACDC  a           schema:MusicGroup ;
        schema:name  "ACDC" .

ex:Starlight  a          schema:MusicRecording ;
        schema:byArtist  ex:Muse ;
        schema:name      "Starlight" .

ex:The_White_Stripes  a  schema:MusicGroup ;
        schema:name  "The White Stripes" .

ex:Adventure_Of_A_Lifetime
        a                schema:MusicRecording ;
        schema:byArtist  ex:Coldplay ;
        schema:name      "Adventure Of A Lifetime" .

ex:Coldplay  a       schema:MusicGroup ;
        schema:name  "Coldplay" .

<http://example.org/Feel_Good_Inc.>
        a                schema:MusicRecording ;
        schema:byArtist  ex:Gorillaz ;
        schema:name      "Feel Good Inc." .

ex:Gorillaz  a       schema:MusicGroup ;
        schema:name  "Gorillaz" .
```

### Input

```
Artist,Title
The Beatles,Come Together
ACDC,Thunderstruck
Coldplay,Adventure Of A Lifetime
The White Stripes,Seven Nation Army
ACDC,You Shook Me All Night Long
Muse,Starlight
Gorillaz,Feel Good Inc.
```
