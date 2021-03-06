# AusPIX Literal

This is the human-readable version of the datatype descriptor for `dggs:auspixLiteral`.

A datatype is a data literal object, identified by an IRI, used by the Resource Description Framework (RDF) [2]. 
Commonly used datatypes in RDF are those defined originally for XML in _W3C XML Schema Definition Language (XSD) 1.1 Part 2: Datatypes_ [1] 
which include fundamental datatypes such as `xsd:string`, `xsd:integer` as well as derived datatypes such as `xsd:nonPositiveInteger`.

This datatype is derived from `xsd:string` and is used to store serializations of geometry descriptors made according to the _AusPIX_ 
Discrete Global Grid System (DGGS) [3]. 

The full IRI defining this datatype is:

* `https://w3id.org/dggs/auspixLiteral`


## Literal contents format

NOTE: A full description of the structure of content within this literal is not complete, however the following description is correct, even though partial.

The following ABNF [4] syntax specification formally defines this literal:

```
auspixLiteral = dggs-type LWSP geometric-data

dggs-type = cell-type / celllist-type / orderedcelllist-type

cell-type = "CELL" LSWP "(" LWSP cell-id LWSP ")"

celllist-type = "CELLLIST" LSWP "((" LWSP *(cell-id LWSP-1) LWSP "))"

orderedcelllist-type = "ORDEREDCELLLIST" LSWP "((" LWSP *(cell-id LWSP-1) LWSP "))"

cell-id = ("N" / "O" / "P" / "Q" / "R" / "S") *(cell-digit)

cell-digit = "0" / "1" / "2" / "3" / "4" / "5" / "6" / "7" / "8"
```

The token `LWSP` is zero or more whitespace characters with newlines permitted.

The token `LWSP-1` is one or more whitespace characters with newlines permitted.


## Examples

```
CELL(R23)
```

```
CELLLIST ((
    R8338506 R8338507 
    R8338508 R8338516 
    R8338530 R8338531 
    R8338532 R8338534 
    R8338540
))
```


## References

[1] Brickley, D. & Guha R.V. (eds) _RDF Schema 1.1_. W3C Recommendation 25 February 2014. https://www.w3.org/TR/rdf-schema/  

[2] Peterson, D. & Gao, S. & Malhotra A. & Sperberg-McQueen C.M. & Thompson, H.S. (eds) _W3C XML Schema Definition Language (XSD) 1.1 Part 2: Datatypes_. W3C Recommendation 5 April 2012. https://www.w3.org/TR/xmlschema11-2/  

[3] Bell, J.G _AusPIX Conceptual Framework for Data Integration based on DGGS Location_. Technical Report, Geoscience Australia (2020). DOI: https://doi.org/10.26186/140152[10.26186/140152]

[4] Internet Engineering Task Force, RFC 5234: Internet Standard 68: Augmented BNF for Syntax Specifications: ABNF. IETF Request for Comment (2008) https://tools.ietf.org/html/std68
