# GA4GH __callset__  

The callset object contains information about an experiment performed on material from a single biosample and is a shared identifier for all variants detected in this experiment, attributed to the referenced biosample. 

## Callset

<table>
<tr>
  <th>property</th>
  <th>type</th>
  <th>format</th>
</tr>
<tr>
  <td>biosample_id</td>
  <td>string</td>
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

### biosample_id

The identifier ("biosample.id") of the biosample this variant was reported from. This is a shortcut to using the variant -> callset -> biosample chaining.

#### Example

```
'biosample_id' : "pgx-bs-987647"
```
### description

A free text description of the callset.

#### Example

```
'description' : "SNP6 array of cancer sample BRCA-0893"
```
### geo_provenance

This geo_class attribute ideally describes the geographic location of where this callset was analysed.


#### Example

```
'geo_provenance' : {
  'city' : 'Timisoara',
  'label' : 'Str Marasesti 5, 300077 Timisoara, Romania',
  'latitude' : 45.75,
  'longitude' : 21.23,
  'country' : 'Romania'
}
```
### id

The local-unique identifier of this callset (referenced as "callset_id").

#### Example

```
'id' : "GSM264198"
```
### info

additional variant information, as defined in the example and accompanying documentation

#### Example

```
'info' : {
  'cnv_maps' : {
                  'schema' : {
                                '$ref' : './common/Info_class'
                              },
                  'value' : {
                               'binning' : {
                                              'value' : 1000000,
                                              'description' : 'interval size in bases for the binning, when creating the cnv_maps',
                                              'type' : 'number',
                                              'format' : 'int64'
                                            },
                               'dup_map' : {
                                              'type' : 'array',
                                              'description' : 'gain cnv status for the corresponding genome intervals
',
                                              'value' : [
                                                           '',
                                                           '',
                                                           'DUP',
                                                           'DUP',
                                                           'DUP',
                                                           '',
                                                           '',
                                                           '',
                                                           '',
                                                           '',
                                                           ''
                                                         ]
                                            }
                             },
                  'description' : 'The cnv_maps object is a wrapper for genomic interval mapped status information. In Progenetix and arrayMap, this is used to indictate - for fixed 1MB genome intervals - the status (dup_map => "DUP" or "", del_map => "DEL" or ""), or the maximum / minimum positive / negative value encountered in the segment, as far as it has been called to contain DUP or DEL.
With a standard binning of 1MB, the arrays would contain ~3000 values each (depending on genome edition).
'
                }
}
```
### updated

time of the last edit of this record, in ISO8601

#### Example

```
'updated' : "2017-10-25T07:06:03Z"
```
