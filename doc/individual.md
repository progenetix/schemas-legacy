# GA4GH __individual__
  

An individual is a single organism (here typically a human).

## Individual

<table>
<tr>
  <th>property</th>
  <th>type</th>
  <th>format</th>
</tr>
<tr>
  <td>biocharacteristics</td>
  <td>array</td>
  <td></td>
</tr>
<tr>
  <td>description</td>
  <td>string</td>
  <td></td>
</tr>
<tr>
  <td>geo_provenance</td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td>id</td>
  <td>string</td>
  <td></td>
</tr>
<tr>
  <td>info</td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td>updated</td>
  <td>string</td>
  <td></td>
</tr>
</table>

### biocharacteristics

list of biocharacteristic_class objects with properly prefixed term ids, describing features of the individual which are not specific to the reported biosample(s); typical examples here are sex, species and "systemic" phenotypes and diseases


#### Example

```
'biocharacteristics' : [
  {
    'class' : {
                 'id' : 'PATO:0020000',
                 'label' : 'female genetic sex'
               },
    'description' : 'girl'
  },
  {
    'class' : {
                 'label' : 'Homo sapiens',
                 'id' : 'NCBITaxon:9606'
               },
    'description' : 'Jean-Luc Picard'
  },
  {
    'description' : 'Patient with Down syndrome',
    'class' : {
                 'id' : 'HP:0003745',
                 'label' : 'Genetic anticipation'
               }
  }
]
```

#### Queries:
the query will return all individuals who have been properly labeled as human
```
db.individual.find( { "biocharacteristics.class.id" : "NCBITaxon:9606" } )
```

this call to the distinct funcion will return *all* HPO annotated classes
```
db.biosamples.distinct( { "biocharacteristics.class.id", "biocharacteristics.class.id" : { $regex : /HP\:/i } } )
```
### description

A free text description of the individual.

#### Example

```
'description' : "patient with lung cancer, male smoker"
```
### geo_provenance

This geo_class attribute ideally describes the geographic location of where this individual originates from.
This value may reflect either the place of burth or residence, but frequently may correspond to the place the study was performed.


#### Example

```
'geo_provenance' : {
  'latitude' : 45.75,
  'altitude' : 94,
  'longitude' : 21.23,
  'country' : 'Romania',
  'city' : 'Timisoara',
  'label' : 'Str Marasesti 5, 300077 Timisoara, Romania'
}
```
### id

The local-unique identifier of this individual (referenced as "individual_id").

#### Example

```
'id' : "AM_BS__NCBISKYCGH-1993"
```
### info

additional variant information, as defined in the example and accompanying documentation

#### Example

```
'info' : {
  'first_name' : {
                    'value' : 'Ion',
                    'type' : 'string'
                  },
  'last_name' : {
                   'type' : 'string',
                   'value' : 'Tichy'
                 }
}
```
### updated

time of the last edit of this record, in ISO8601

#### Example

```
'updated' : "2017-10-25T07:06:03Z"
```
