# SPARQL Anything resources

This repository collects links and resources for the class on SPARQL Anything that will take place on December 16th in the context of the [Knowledge Engineering course](https://www.unibo.it/it/didattica/insegnamenti/insegnamento/2021/446613).

## Video Tutorial and Slides

## SPARQL Anything documentation

## Homework

Goal: Design a SPARQL Anything construct query that extracts the following Knowledge Graph from [this input file](https://raw.githubusercontent.com/luigi-asprino/knowledge-engineering/master/COLLEZIONE_GAM.json).

```turtle
@prefix arco:  <https://w3id.org/arco/ontology/arco/> .
@prefix ex:    <http://example.org/> .
@prefix rdf:   <http://www.w3.org/2000/01/rdf-schema#> .
@prefix rdfs:  <http://www.w3.org/2000/01/rdf-schema#> .
@prefix arco-cd: <https://w3id.org/arco/ontology/context-description/> .

ex:MORELLI_Domenico  rdf:label  "MORELLI Domenico" .

ex:Schizzi_di_figure  a  arco:CulturalProperty ;
        rdf:label  "Schizzi di figure" .

ex:MORELLI_Domenico_Pagina_di_taccuino_con_scritta
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  ex:MORELLI_Domenico ;
        arco-cd:isAuthorshipAttributionOf
                ex:Pagina_di_taccuino_con_scritta .

<http://example.org/LUND_J._(?)_Schizzo_caricaturale_di_Domenico_Morelli>
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  <http://example.org/LUND_J._(?)> ;
        arco-cd:isAuthorshipAttributionOf
                ex:Schizzo_caricaturale_di_Domenico_Morelli .

ex:MORELLI_Domenico_Schizzi_di_figure
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  ex:MORELLI_Domenico ;
        arco-cd:isAuthorshipAttributionOf
                ex:Schizzi_di_figure .

<http://example.org/LUND_J._(?)_Autoritratto_a_16_anni>
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  <http://example.org/LUND_J._(?)> ;
        arco-cd:isAuthorshipAttributionOf
                ex:Autoritratto_a_16_anni .

<http://example.org/LUND_J._(?)_Pagina_di_taccuino_con_scritta>
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  <http://example.org/LUND_J._(?)> ;
        arco-cd:isAuthorshipAttributionOf
                ex:Pagina_di_taccuino_con_scritta .

ex:MORELLI_Domenico_Caricature
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  ex:MORELLI_Domenico ;
        arco-cd:isAuthorshipAttributionOf
                ex:Caricature .

ex:Pagina_di_taccuino_con_scritta
        a          arco:CulturalProperty ;
        rdf:label  "Pagina di taccuino con scritta" .

ex:MORELLI_Domenico_Autoritratto
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  ex:MORELLI_Domenico ;
        arco-cd:isAuthorshipAttributionOf
                ex:Autoritratto .

ex:Autoritratto_a_16_anni
        a          arco:CulturalProperty ;
        rdf:label  "Autoritratto a 16 anni" .

ex:MORELLI_Domenico_Autoritratto_a_16_anni
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  ex:MORELLI_Domenico ;
        arco-cd:isAuthorshipAttributionOf
                ex:Autoritratto_a_16_anni .

ex:Autoritratto_a_28_anni
        a          arco:CulturalProperty ;
        rdf:label  "Autoritratto a 28 anni" .

<http://example.org/LUND_J._(?)>
        rdf:label  "LUND J. (?)" .

ex:Proiezioni_geometriche
        a          arco:CulturalProperty ;
        rdf:label  "Proiezioni geometriche" .

ex:MORELLI_Domenico_Autoritratto_a_28_anni
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  ex:MORELLI_Domenico ;
        arco-cd:isAuthorshipAttributionOf
                ex:Autoritratto_a_28_anni .

ex:Studio_di_panneggio
        a          arco:CulturalProperty ;
        rdf:label  "Studio di panneggio" .

<http://example.org/LUND_J._(?)_Schizzi_di_figure>
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  <http://example.org/LUND_J._(?)> ;
        arco-cd:isAuthorshipAttributionOf
                ex:Schizzi_di_figure .

ex:MORELLI_Domenico_Proiezioni_geometriche
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  ex:MORELLI_Domenico ;
        arco-cd:isAuthorshipAttributionOf
                ex:Proiezioni_geometriche .

<http://example.org/LUND_J._(?)_Studio_di_panneggio>
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  <http://example.org/LUND_J._(?)> ;
        arco-cd:isAuthorshipAttributionOf
                ex:Studio_di_panneggio .

ex:Caricature  a   arco:CulturalProperty ;
        rdf:label  "Caricature" .

ex:Autoritratto  a  arco:CulturalProperty ;
        rdf:label  "Autoritratto" .

ex:MORELLI_Domenico_Studio_di_panneggio
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  ex:MORELLI_Domenico ;
        arco-cd:isAuthorshipAttributionOf
                ex:Studio_di_panneggio .

ex:Schizzo_caricaturale_di_Domenico_Morelli
        a          arco:CulturalProperty ;
        rdf:label  "Schizzo caricaturale di Domenico Morelli" .

ex:MORELLI_Domenico_Schizzo_caricaturale_di_Domenico_Morelli
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  ex:MORELLI_Domenico ;
        arco-cd:isAuthorshipAttributionOf
                ex:Schizzo_caricaturale_di_Domenico_Morelli .

<http://example.org/LUND_J._(?)_Autoritratto_a_28_anni>
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  <http://example.org/LUND_J._(?)> ;
        arco-cd:isAuthorshipAttributionOf
                ex:Autoritratto_a_28_anni .

<http://example.org/LUND_J._(?)_Proiezioni_geometriche>
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  <http://example.org/LUND_J._(?)> ;
        arco-cd:isAuthorshipAttributionOf
                ex:Proiezioni_geometriche .

<http://example.org/LUND_J._(?)_Autoritratto>
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  <http://example.org/LUND_J._(?)> ;
        arco-cd:isAuthorshipAttributionOf
                ex:Autoritratto .

<http://example.org/LUND_J._(?)_Caricature>
        a                            arco-cd:AuthorshipAttribution ;
        arco-cd:hasAttributedAuthor  <http://example.org/LUND_J._(?)> ;
        arco-cd:isAuthorshipAttributionOf
                ex:Caricature .
```
