# Progenetix Schemas

**Schemas for Progenetix can now be found inside the [`bycon`](http://github.com/progenetix/bycon) project with additional info on the [Progenetix documentation site](http://docs.progenetix.org).**

<img src="rsrc/img/ga4gh-object-model.png" align="right" />

## schemas

This repository contains the data schemas for the Progenetix databases (i.e. the backend behind [progenetix.org](http://progenetix.org)) and the [Beacon+](http://beacon.progenetix.org/ui/) project.

The files here represent stable/recent versions of schemas used in  [**bycon**](https://github.com/progenetix/bycon/), a project which provides server and middleware for a Beacon solution on top of a set of MongoDB databases.

The main schemas have been developed as part of the [GA4GH Metadata Schemas](https://github.com/ga4gh-metadata/metadata-schemas/tree/master/schemas) which had also served for the development of the [Phenopackets](https://github.com/phenopackets/phenopacket-schema/). Current Progenetix schemas closely track and align with Phenopackets and the Beacon v2 API.

The primary YAML documents here are in the [schemas](./schemas/) directory:

* `Variant`
    The `variant` object includes attributes and examples for both structural (DUP, DEL, BRK) and precise genome variants.
* `Callset`
    The `callset` object is for technoical data and series information (e.g. used platform and analysis metods). It is not strictly needed for querying combined variant + biosample aspects, since in the current implementation the `variant` object contains a reference to the `biosample` it was derived from.
* `Biosample`
    Most relevant "bio"data (such as diagnoses, phenotypes ...) is stored in the `biosample` object.
* `Individual`
    The `individual` object contains information which pertains to the whole biological entity biosamples are derived from (e.g. sex, heritable phenotypes...).
    
Other schemas in the repository are components of those main schemas or are part of the Progenetix resource environment.

    
    
