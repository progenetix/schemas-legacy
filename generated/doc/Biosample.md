
<div id="schema-header-title">
  <h2>Biosample <span id="schema-header-title-project">progenetix <a href="https://github.com/progenetix/schemas" target="_BLANK">&nearr;</a></span> </h2>
</div>

<table id="schema-header-table">
  <tr>
    <th>{S}[B] Status <a href="https://schemablocks.org/about/sb-status-levels.html">[i]</a></th>
    <td><div id="schema-header-status">external</div></td>
  </tr>

  <tr>
    <th>Provenance</th>
    <td>
      <ul>
<li><a href="https://progenetix.org">Progenetix cancer genome profiling resource</a></li>
      </ul>
    </td>
  </tr>
  <tr>
    <th>Used by</th>
    <td>
      <ul>
<li><a href="https://progenetix.org">Progenetix</a></li>
<li><a href="https://progenetix.org">Progenetix</a></li>
      </ul>
    </td>
  </tr>

<!--more-->

  <tr>
    <th>Contributors</th>
    <td>
      <ul>
<li><a href="https://orcid.org/0000-0002-9903-4248">Michael Baudis</a></li>
<li>Bo Gao</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th>Source (v2020-02-12)</th>
    <td>
      <ul>
        <li><a href="current/Biosample.json" target="_BLANK">raw source [JSON]</a></li>
        <li><a href="https://github.com/progenetix/schemas/blob/master/schemas/Biosample.yaml" target="_BLANK">Github</a></li>
      </ul>
    </td>
  </tr>
</table>

<div id="schema-attributes-title">
  <h3>Attributes</h3>
</div>

  
__Type:__ object  
__Description:__ In this schema, a "biosample" as the source of the material of a molecular analysis (e.g. genomic array, sequencing), represents the main “biological item” against which molecular variants are referenced.

### Properties

<table id="schema-properties-table">
  <tr>
    <th>Property</th>
    <th>Type</th>
  </tr>
  <tr>
    <th>age_at_collection</th>
    <td>https://schemablocks.org/schemas/sb-phenopackets/v1.0.0/Age.json [<a href="https://schemablocks.org/schemas/sb-phenopackets/v1.0.0/Age.json" target="_BLANK">SRC</a>] [<a href="https://schemablocks.org/schemas/sb-phenopackets/Age.html" target="_BLANK">HTML</a>]</td>
  </tr>
  <tr>
    <th>biocharacteristics</th>
    <td>array of ./ExtendedClass.json [<a href="./ExtendedClass.json" target="_BLANK">SRC</a>] [<a href="./ExtendedClass.html" target="_BLANK">HTML</a>]</td>
  </tr>
  <tr>
    <th>created</th>
    <td>string</td>
  </tr>
  <tr>
    <th>data_use_conditions</th>
    <td>https://schemablocks.org/schemas/sb-phenopackets/v1.0.0/OntologyClass.json [<a href="https://schemablocks.org/schemas/sb-phenopackets/v1.0.0/OntologyClass.json" target="_BLANK">SRC</a>] [<a href="https://schemablocks.org/schemas/sb-phenopackets/OntologyClass.html" target="_BLANK">HTML</a>]</td>
  </tr>
  <tr>
    <th>description</th>
    <td>string</td>
  </tr>
  <tr>
    <th>external_references</th>
    <td>array of ./ExtendedClass.json [<a href="./ExtendedClass.json" target="_BLANK">SRC</a>] [<a href="./ExtendedClass.html" target="_BLANK">HTML</a>]</td>
  </tr>
  <tr>
    <th>id</th>
    <td>string</td>
  </tr>
  <tr>
    <th>individualId</th>
    <td>string</td>
  </tr>
  <tr>
    <th>info</th>
    <td>./Info.json [<a href="./Info.json" target="_BLANK">SRC</a>] [<a href="./Info.html" target="_BLANK">HTML</a>]</td>
  </tr>
  <tr>
    <th>provenance</th>
    <td>./ProvenanceClass.json [<a href="./ProvenanceClass.json" target="_BLANK">SRC</a>] [<a href="./ProvenanceClass.html" target="_BLANK">HTML</a>]</td>
  </tr>
  <tr>
    <th>updated</th>
    <td>string</td>
  </tr>

</table>


#### age_at_collection

* type: https://schemablocks.org/schemas/sb-phenopackets/v1.0.0/Age.json [<a href="https://schemablocks.org/schemas/sb-phenopackets/v1.0.0/Age.json" target="_BLANK">SRC</a>] [<a href="https://schemablocks.org/schemas/sb-phenopackets/Age.html" target="_BLANK">HTML</a>]

An age object describing the age of the individual this biosample was
derived from at the time of collection. The Age object allows the encoding
of the age either as ISO8601 duration or time interval (preferred), or
as ontology term object.
See http://build.fhir.org/datatypes


##### `age_at_collection` Value Example  

```
{
   "age" : "P48Y3M"
}
```

#### biocharacteristics

* type: array of ./ExtendedClass.json [<a href="./ExtendedClass.json" target="_BLANK">SRC</a>] [<a href="./ExtendedClass.html" target="_BLANK">HTML</a>]

"biocharacteristics" represents a wrapper list of "ExtendedClass" objects with properly prefixed term ids, describing features of the biosample.
Examples would be phenotypes, disease codes or other ontology classes specific to this biosample. In a complete data model (variants - (callsets) - biosamples - individuals), characteristics applying to the individual (e.g. sex, most phenotypes) should be annotated there.


##### `biocharacteristics` Value Example  

```
[
   {
      "class" : {
         "id" : "icdot:C25.9",
         "label" : "Pancreas, NOS"
      },
      "description" : "Pancreatic Adenocarcinoma"
   },
   {
      "class" : {
         "id" : "icdom:81403",
         "label" : "Adenocarcinoma, NOS"
      },
      "description" : "Pancreatic Adenocarcinoma"
   },
   {
      "class" : {
         "id" : "ncit:C8294",
         "label" : "Pancreatic Adenocarcinoma"
      },
      "description" : "Pancreatic Adenocarcinoma"
   }
]
```

#### created

* type: string

The creation time of this record, in ISO8601


##### `created` Value Example  


#### data_use_conditions

* type: https://schemablocks.org/schemas/sb-phenopackets/v1.0.0/OntologyClass.json [<a href="https://schemablocks.org/schemas/sb-phenopackets/v1.0.0/OntologyClass.json" target="_BLANK">SRC</a>] [<a href="https://schemablocks.org/schemas/sb-phenopackets/OntologyClass.html" target="_BLANK">HTML</a>]

Data use conditions applying to data from this biosample, as ontology object (e.g. DUO).


##### `data_use_conditions` Value Example  

```
{
   "id" : "DUO:0000004",
   "label" : "no restriction"
}
```

#### description

* type: string

The biosample's description. This attribute contains human readable text.
The "description" attributes should not contain any structured data.


##### `description` Value Example  

```
"Burkitt lymphoma, cell line Namalwa"
```

#### external_references

* type: array of ./ExtendedClass.json [<a href="./ExtendedClass.json" target="_BLANK">SRC</a>] [<a href="./ExtendedClass.html" target="_BLANK">HTML</a>]

list of reference_class objects with properly (e.g. identifiers.org) 
prefixed external identifiers and a term describing the relationship


##### `external_references` Value Example  

```
[
   {
      "description" : "Human Bone Osteosarcoma cell line",
      "type" : {
         "id" : "cellosaurus:CVCL_0312",
         "label" : "HOS"
      }
   },
   {
      "description" : "Article: Greshock et al.: Cancer cell lines as genetic models of their parent histology",
      "relation" : "report",
      "type" : {
         "id" : "pubmed:17440070"
      }
   }
]
```

#### id

* type: string

The local-unique identifier of this biosample (referenced as
"biosample_id"). This is unique in the context of the local (e.g.
server, resource) instance.


##### `id` Value Example  

```
"SAMN05324082"
```

#### individualId

* type: string

In a complete data model "individual_id" points to the "id" of the
individual ("donor", "subjerct"...) this _Biosample_ was derived from.

In a local context this could be the _id_ attribute in a corresponding
"individuals" collection.


##### `individualId` Value Example  

```
"SAMN05324082-individual"
```

#### info

* type: ./Info.json [<a href="./Info.json" target="_BLANK">SRC</a>] [<a href="./Info.html" target="_BLANK">HTML</a>]

This is a wrapper for objects without further specification in the schema.


##### `info` Value Example  

```
[
   {
      "death" : "1",
      "followup_time" : "P14M"
   }
]
```

#### provenance

* type: ./ProvenanceClass.json [<a href="./ProvenanceClass.json" target="_BLANK">SRC</a>] [<a href="./ProvenanceClass.html" target="_BLANK">HTML</a>]

Aspects such as geographic origin or material type, processing,
providing additional information about the biosample.


##### `provenance` Value Example  

```
[
   {
      "geo" : {
         "city" : "New York City",
         "country" : "United States",
         "geojson" : {
            "coordinates" : [
               "74.01",
               "40.71"
            ],
            "type" : "Point"
         },
         "label" : "New York City, United States",
         "latitude" : "40.71",
         "longitude" : "-74.01",
         "precision" : "city"
      },
      "material" : {
         "description" : "normal cervix",
         "type" : {
            "id" : "EFO:0009654",
            "label" : "reference sample"
         }
      }
   }
]
```

#### updated

* type: string

The time of the last edit of this record, in ISO8601


##### `updated` Value Example  



### `Biosample` Value Example  


