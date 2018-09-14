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
  <td>$property</td>
  <td>$attr{$class}->{properties}->{$property}->{type}</td>
  <td>$attr{$class}->{properties}->{$property}->{format}</td>
</tr>
<tr>
  <td>$property</td>
  <td>$attr{$class}->{properties}->{$property}->{type}</td>
  <td>$attr{$class}->{properties}->{$property}->{format}</td>
</tr>
<tr>
  <td>$property</td>
  <td>$attr{$class}->{properties}->{$property}->{type}</td>
  <td>$attr{$class}->{properties}->{$property}->{format}</td>
</tr>
<tr>
  <td>$property</td>
  <td>$attr{$class}->{properties}->{$property}->{type}</td>
  <td>$attr{$class}->{properties}->{$property}->{format}</td>
</tr>
<tr>
  <td>$property</td>
  <td>$attr{$class}->{properties}->{$property}->{type}</td>
  <td>$attr{$class}->{properties}->{$property}->{format}</td>
</tr>
<tr>
  <td>$property</td>
  <td>$attr{$class}->{properties}->{$property}->{type}</td>
  <td>$attr{$class}->{properties}->{$property}->{format}</td>
</tr>### biocharacteristics

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
                 'id' : 'NCBITaxon:9606',
                 'label' : 'Homo sapiens'
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
  'longitude' : 21.23,
  'country' : 'Romania',
  'latitude' : 45.75,
  'label' : 'Str Marasesti 5, 300077 Timisoara, Romania',
  'city' : 'Timisoara',
  'altitude' : 94
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
  'last_name' : {
                   'value' : 'Tichy',
                   'type' : 'string'
                 },
  'first_name' : {
                    'value' : 'Ion',
                    'type' : 'string'
                  }
}
```
### updated

time of the last edit of this record, in ISO8601

#### Example

```
'updated' : "2017-10-25T07:06:03Z"
```
