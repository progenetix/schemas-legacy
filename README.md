!(GA4GH legacy schema)["./rsrc/img/ga4gh-object-model.png"]

## schemas

This repository contains the data schemas for the Progenetix databases (i.e. the backends behind [progenetix.org](http://progenetix.org). [arraymap.org](http://arraymap.org)) and the [Beacon+](http://beacon.progenetix.org/ui/) project.

The primary YAML documents are in the [schemas](./schemas/) directory, with JSON versions and examples extracted from them. The "readable" documentation is also created from the YAML files and can be accessed here:

* `Variant`
    The `variant` object includes attributes and examples for both structural (DUP, DEL, BRK) and precise genome variants.
* `Callset`
    The `callset` object is for technoical data and series information (e.g. used platform and analysis metods). It is not strictly needed for querying combined variant + biosample aspects, since in the current implementation the `variant` object contains a reference to the `biosample` it was derived from.
* `Biosample`
    Most relevant "bio"data (such as diagnoses, phenotypes ...) is stored in the `biosample` object.
* `Individual`
    The `individual` object contains information which pertains to the whole biological entity biosamples are derived from (e.g. sex, heritable phenotypes...).
    

    
    
