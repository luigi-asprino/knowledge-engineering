# SPARQL Anything resources

This repository collects links and resources for the [Knowledge Engineering class](https://www.unibo.it/it/didattica/insegnamenti/insegnamento/2021/446613) class on SPARQL Anything that will take place on December 14th.

## Video Tutorial and Slides

- [Video Tutorial](https://www.dropbox.com/s/bc31v0klg68op0z/SPARQLAnythingTutorial-highres.mp4?dl=0)
- [Slides](https://www.dropbox.com/s/6t7e6ehwkpvaf5b/AGentleIntroductionToSPARQLAnything.pdf?dl=0)
- [CONSTRUCT query](https://raw.githubusercontent.com/luigi-asprino/knowledge-engineering/master/query_slides.rq)


## SPARQL Anything links

-  [Website](https://sparql-anything.cc/)
-  [Documentation](https://sparql-anything.readthedocs.io/en/latest/) (Please use the release [v0.5.1](https://github.com/SPARQL-Anything/sparql.anything/releases/tag/v0.5.1))
-  [GitHub Repository](https://github.com/SPARQL-Anything/sparql.anything)
-  [Releases](https://github.com/SPARQL-Anything/sparql.anything/releases)
- [Live Demo](http://90.147.189.232:9000/sparql)
-  [Showcase IMMA](https://github.com/SPARQL-Anything/showcase-imma) [Showcase Propbank](https://github.com/SPARQL-Anything/showcase-propbank) [Showcase Tate Gallery](https://github.com/SPARQL-Anything/showcase-tate)
-  **Important**: once you have completed the assignments please take a few minutes to fill out our survey on [Knowledge Graph Construction](https://docs.google.com/forms/d/e/1FAIpQLSfbnGLug1jgqe7ixGvIGPHtS6YvksreNOEj5nU59-9MON6TDQ/viewform?usp=sf_link). 
-  [Share your **solution**](https://docs.google.com/document/d/1LgHaXqE4vYrho2RM5zq8aQTtY_AKhtYLsi6Sb2fSuPw/edit?usp=sharing)

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

## Assignment 3

Goal: Designing a SPARQL Anything construct query that extracts the following [target Knowledge Graph](https://raw.githubusercontent.com/luigi-asprino/knowledge-engineering/master/target_kg_3.ttl) from [this input file](https://raw.githubusercontent.com/luigi-asprino/knowledge-engineering/master/assignment_3.xml).

### Target KG

```turtle
@prefix ex:    <http://example.org/> .
@prefix rdf:   <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix fabio: <http://purl.org/spar/fabio/> .
@prefix dcterms: <http://purl.org/dc/terms/> .
@prefix foaf:  <http://xmlns.com/foaf/0.1/> .

<http://example.org/Thurman,_Paula>
        a          foaf:Agent ;
        foaf:name  "Thurman, Paula" .

ex:bk104  a                  fabio:Book ;
        dcterms:creator      <http://example.org/Corets,_Eva> ;
        dcterms:description  "In post-apocalypse England, the mysterious\n      agent known only as Oberon helps to create a new life\n      for the inhabitants of London. Sequel to Maeve\n      Ascendant." ;
        dcterms:title        "Oberon's Legacy" .

<http://example.org/Corets,_Eva>
        a          foaf:Agent ;
        foaf:name  "Corets, Eva" .

ex:bk102  a                  fabio:Book ;
        dcterms:creator      <http://example.org/Ralls,_Kim> ;
        dcterms:description  "A former architect battles corporate zombies,\n      an evil sorceress, and her own childhood to become queen\n      of the world." ;
        dcterms:title        "Midnight Rain" .

ex:bk107  a                  fabio:Book ;
        dcterms:creator      <http://example.org/Thurman,_Paula> ;
        dcterms:description  "A deep sea diver finds true love twenty\n      thousand leagues beneath the sea." ;
        dcterms:title        "Splish Splash" .

<http://example.org/Ralls,_Kim>
        a          foaf:Agent ;
        foaf:name  "Ralls, Kim" .

ex:bk105  a                  fabio:Book ;
        dcterms:creator      <http://example.org/Corets,_Eva> ;
        dcterms:description  "The two daughters of Maeve, half-sisters,\n      battle one another for control of England. Sequel to\n      Oberon's Legacy." ;
        dcterms:title        "The Sundered Grail" .

<http://example.org/Randall,_Cynthia>
        a          foaf:Agent ;
        foaf:name  "Randall, Cynthia" .

ex:bk103  a                  fabio:Book ;
        dcterms:creator      <http://example.org/Corets,_Eva> ;
        dcterms:description  "After the collapse of a nanotechnology\n      society in England, the young survivors lay the\n      foundation for a new society." ;
        dcterms:title        "Maeve Ascendant" .

<http://example.org/Gambardella,_Matthew>
        a          foaf:Agent ;
        foaf:name  "Gambardella, Matthew" .

ex:bk101  a                  fabio:Book ;
        dcterms:creator      <http://example.org/Gambardella,_Matthew> ;
        dcterms:description  "An in-depth look at creating applications\n      with XML." ;
        dcterms:title        "XML Developer's Guide" .

ex:bk106  a                  fabio:Book ;
        dcterms:creator      <http://example.org/Randall,_Cynthia> ;
        dcterms:description  "When Carla meets Paul at an ornithology\n      conference, tempers fly as feathers get ruffled." ;
        dcterms:title        "Lover Birds" .
```

### Input
```turtle
<?xml version="1.0"?>
<catalog>
   <book id="bk101">
      <author>Gambardella, Matthew</author>
      <title>XML Developer's Guide</title>
      <genre>Computer</genre>
      <price>44.95</price>
      <publish_date>2000-10-01</publish_date>
      <description>An in-depth look at creating applications
      with XML.</description>
   </book>
   <book id="bk102">
      <author>Ralls, Kim</author>
      <title>Midnight Rain</title>
      <genre>Fantasy</genre>
      <price>5.95</price>
      <publish_date>2000-12-16</publish_date>
      <description>A former architect battles corporate zombies,
      an evil sorceress, and her own childhood to become queen
      of the world.</description>
   </book>
   <book id="bk103">
      <author>Corets, Eva</author>
      <title>Maeve Ascendant</title>
      <genre>Fantasy</genre>
      <price>5.95</price>
      <publish_date>2000-11-17</publish_date>
      <description>After the collapse of a nanotechnology
      society in England, the young survivors lay the
      foundation for a new society.</description>
   </book>
   <book id="bk104">
      <author>Corets, Eva</author>
      <title>Oberon's Legacy</title>
      <genre>Fantasy</genre>
      <price>5.95</price>
      <publish_date>2001-03-10</publish_date>
      <description>In post-apocalypse England, the mysterious
      agent known only as Oberon helps to create a new life
      for the inhabitants of London. Sequel to Maeve
      Ascendant.</description>
   </book>
   <book id="bk105">
      <author>Corets, Eva</author>
      <title>The Sundered Grail</title>
      <genre>Fantasy</genre>
      <price>5.95</price>
      <publish_date>2001-09-10</publish_date>
      <description>The two daughters of Maeve, half-sisters,
      battle one another for control of England. Sequel to
      Oberon's Legacy.</description>
   </book>
   <book id="bk106">
      <author>Randall, Cynthia</author>
      <title>Lover Birds</title>
      <genre>Romance</genre>
      <price>4.95</price>
      <publish_date>2000-09-02</publish_date>
      <description>When Carla meets Paul at an ornithology
      conference, tempers fly as feathers get ruffled.</description>
   </book>
   <book id="bk107">
      <author>Thurman, Paula</author>
      <title>Splish Splash</title>
      <genre>Romance</genre>
      <price>4.95</price>
      <publish_date>2000-11-02</publish_date>
      <description>A deep sea diver finds true love twenty
      thousand leagues beneath the sea.</description>
   </book>
 </catalog>
```
