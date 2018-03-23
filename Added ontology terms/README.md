# Adding ontology terms

* Author: Egon Willighagen
* License: CC-BY 4.0

This ontology describes how terms can be added to the eNanoMapper ontology.
Before walking through this tutorial, it is recommended to read the following
documents:

* Article: [eNanoMapper: harnessing ontologies to enable data integration for nanomaterial risk assessment](https://jbiomedsem.biomedcentral.com/articles/10.1186/s13326-015-0005-5)
* Deliverable Report D2.1 [Framework and Infrastructure for Ontology development, versioning and dissemination](http://doi.org/10.5281/zenodo.375633)
* Deliverable Report D2.2 [Ontology Content Types and Existing Community efforts](http://doi.org/10.5281/zenodo.375634)
* Deliverable Report D2.3 [Ontology initial release](http://doi.org/10.5281/zenodo.375635)
* Deliverable Report D2.4 [Ontology final release](http://doi.org/10.5281/zenodo.375633)

# A collection on ontology parts

The eNanoMapper ontology is mostly composed of other ontologies. A list of ontologies it includes includes
the following:

* AOP
* BAO
* BFO
* CCONT
* CHEBI
* CHEMINF
* CHMO
* EFO
* ENVO
* FABIO
* GO
* HUPSON
* IAO
* NCIT
* NPO
* OAE
* OBCS
* OBI
* PATO
* SIO
* UO

However, the eNanoMapper ontology does not use full ontologies, and there are
reasons why that is essential:

* most ontologies include bits from other ontologies; and,
* some ontologies do not just have core concepts, but enumerate hundreds or thousands of instances.

Therefore, we select parts of ontologies. In order to perform this slicing we need a tool that can do this
slicing and we need to instruct this slices which bits to keep.

# The configuration file

Configuration file are used to define which parts of which ontologies are used. These configuration files
can be [found on GitHub](https://github.com/enanomapper/ontologies/tree/master/config). For each ontology,
two files are provided:

1. an .props file
2. an .iris file

## The *props* file

The first "props" file is the one initially read by the [Slimmer tool]() and looks like:

```
owl=https://raw.githubusercontent.com/enanomapper/aop-ontology/patch/hpoUpdate/aopo.owl
iris=aopo.iris
slimmed=http://purl.enanomapper.org/onto/external/aopo-slim.owl
```

It has three fields. The *owl* field indicates where the ontology can be downloaded (this is normally an
upstream location, but a cached version in this particular case). The *iris* field points to the second
configuration file. The *slimmed* field defines the URL of the slimmed ontology. That URL is used for
*owl:import* statements in the eNanoMapper ontology, which is the used mechanism to include slimmed
ontology modules.

## The *iris* file

The second configuration file defined the input to the slimming process and specifies what parts are meant
to be kept. The format is a custom format specifically developed for our slimming needs.

....

# Adding terms

## Adding a terms from an already used ontology


## Adding a terms from an ontology that is not yet used




# Acknowledgments

This tutorial was written as part of the OpenRiskNet and NanoCommons projects. OpenRiskNet (Grant Agreement
[731075](http://cordis.europa.eu/projects/731075)) and NanoCommons (Grant Agreement 
[731032](http://cordis.europa.eu/projects/731032)) are projects
funded by the European Commission within Horizon2020 Programme


