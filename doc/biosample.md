
### _id

the database-internal object id

* example: `ObjectId("558e5c56ad9a82d958392bd6")`

### age_at_collection

the age of the individual at time of biosample collection, as ISO8601 string

* example: `P56Y`

### age_at_collection_class

the age of the individual at time of biosample collection, as ontology object

* example: `HASH(0x7fb63c80da60)`

### biocharacteristics

"biocharacteristics" represents a wrapper list of "biocharacteristic_class" objects with properly prefixed term ids, describing features of the biosample.
Examples would be phenotypes, disease codes or other ontology classes specific to this biosample. In a complete data model (variants - (callsets) - biosamples - individuals), characteristics applying to the individual (e.g. sex, most phenotypes) should be annotated there.


* example: 
```
[
  {
    'description' => 'Pancreatic Adenocarcinoma',
    'class' => {
                 'id' => 'pgx:icdot:c25.9',
                 'label' => 'Pancreas, NOS'
               }
  },
  {
    'description' => 'Pancreatic Adenocarcinoma',
    'class' => {
                 'id' => 'pgx:icdom:81403',
                 'label' => 'Adenocarcinoma, NOS'
               }
  },
  {
    'class' => {
                 'label' => 'Pancreatic Adenocarcinoma',
                 'id' => 'ncit:c8294'
               },
    'description' => 'Pancreatic Adenocarcinoma'
  }
]

```

### description

A free text description of the biosample.

* example: `Burkitt lymphoma, cell line Namalwa`

### external_ids

list of reference_class objects with properly (e.g. identifiers.org) prefixed external identifiers and a term describing the relationship

* example: 
```
[
  {
    'relation' => 'provenance',
    'id' => 'cellosaurus:CVCL_0312'
  },
  {
    'relation' => 'report',
    'id' => 'pubmed:17440070'
  },
  {
    'id' => 'geo:GPL4894',
    'relation' => 'technology'
  },
  {
    'id' => 'geo:GSM185088',
    'relation' => 'denotes'
  }
]

```

### geo_provenance

This geo_class attribute ideally describes the geographic location of where the sample was extracted.
Frequently this value may reflect either the place of the laboratory where the analysis was performed, or correspond to the corresponding author's institution.


* example: 
```
[
  {
    'label' => 'Str Marasesti 5, 300077 Timisoara, Romania',
    'city' => 'Timisoara',
    'latitude' => '45.75',
    'country' => 'Romania',
    'altitude' => 94,
    'longitude' => '21.23'
  }
]

```

### id

The local-unique identifier of this biosample (referenced as "biosample_id").

* example: `AM_BS__NCBISKYCGH-1993`

### individual_id

In a complete data model "individual_id" represents the identifier of this biosample in the "individuals" collection.


* example: `ind-cnhl-1293347-004`

### info

This is a list for objects without further specification in the schema.


* example: 
```
[
  {
    'name' => 'followup_time',
    'value' => 'P14M',
    'type' => 'ISO8601 string'
  },
  {
    'value' => 1,
    'name' => 'death',
    'type' => 'boolean'
  }
]

```

### updated

time of the last edit of this record, in ISO8601

* example: `2017-10-25T07:06:03Z`
