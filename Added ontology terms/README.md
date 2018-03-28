# Adding ontology terms

* Author: Egon Willighagen (orcid:[0000-0001-7542-0286](https://orcid.org/0000-0001-7542-0286))
* License: [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/)
* Source: [https://github.com/enanomapper/tutorials/tree/master/Added%20ontology%20terms](https://github.com/enanomapper/tutorials/tree/master/Added%20ontology%20terms)

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

* [Adverse Outcome Pathways Ontology](https://github.com/DataSciBurgoon/aop-ontology) (AOP)
* [BioAssay Ontology](http://bioassayontology.org/) (BAO)
* [Basic Formal Ontology](http://basic-formal-ontology.org/) (BFO)
* CCONT
* [Chemical Entities of Biological Interest](https://www.ebi.ac.uk/chebi/) (CHEBI)
* [Chemical Information Ontology](https://github.com/semanticchemistry/semanticchemistry/) (CHEMINF)
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

The first "props" file is the one initially read by the [Slimmer tool](https://github.com/enanomapper/slimmer) and looks like:

```
owl=https://raw.githubusercontent.com/enanomapper/aop-ontology/patch/hpoUpdate/aopo.owl
iris=aopo.iris
slimmed=http://purl.enanomapper.org/onto/external/aopo-slim.owl
```

It has three fields as explained in the following subsections

### Source ontology file

The `owl=` line indicates where the OWL file of the ontology to be slimmed can be downloaded (this is normally an
upstream location, but a cached version in this particular case). It is exactly this OWL file that is loaded by the OWLAPI-based Slimmer utility, and slimmed.

### Specifying the configuration

The `iris=` line indicates the configuration file is found locally which defines which IRIs are to be included and excluded in the slimmed version of the ontology. The syntax of the `.iris` file is discussed below.

### The slimmed ontology file

The `slimmer=` line specifies the file name under which the resulting slimmed ontology is saved. It is this
file that is to be imported by the main eNanoMapper OWL file. That is, this URL is used for
*owl:import* statements in the eNanoMapper ontology, which is the used mechanism to include slimmed
ontology modules.

## The *iris* file

The second configuration file defined the input to the slimming process and specifies what parts are meant
to be kept. The format is a custom format specifically developed for our slimming needs.

The `.iris` file configures the slicing of the ontology. It specifies which classes or class tress to include and which parts to exclude. For each included class it can also specify a new classes it subclasses. Each line in this file defines one instruction: one addition or one removal.

For example:
```
+D(http://purl.bioontology.org/ontology/npo#NPO_1436):http://www.bioassayontology.org/bao#BAO_0000697 detection instrument
+D(http://purl.obolibrary.org/obo/IAO_0000030):http://www.bioassayontology.org/bao#BAO_0000179 endpoint
+D(http://purl.obolibrary.org/obo/OBI_0000070):http://www.bioassayontology.org/bao#BAO_0000015 bioassay
````

This configuration file uses a custom syntax which is briefly explained here.
Here, the first line in the above example shows that the term detection instrument is imported (from the BAO ontology) and made a subclass of the NPO_1436 class from the NPO ontoloy.

### The Syntax

Each instruction has the same structure, the same syntax, organized in layers:

![Syntax of a Slimmer instruction.](syntax.png)

We can see here basically the five layers (red, yellow, green, purple, and blue) and in semi-colon (light blue) to
separate two layers. Each layer is introduced below.

### Adding and removing (red layer)

 By default it removes all content. The first character indicates if the something needs to be included (+) or excluded from a previously defined inclusion (-). The second character indicates whether a whole upper (U) or down (D) tree should be included or excluded. After the colon the URI of the resource is given to be in- or excluded, followed by a user-oriented comment. Finally, before the colon and in brackets an optional superclass of this resource can be specified, possibly from other ontologies.


The

# Adding terms

Adding terms to the eNanoMapper ontology is basically equivalent to making changes or adding such configuration files.
If the ontology already exists, then you basically change the content of the *iris* file. If you need a new ontology
from which you want to include terms, then you need to create a new combination of a *props* and an *iris* file. This
is explained in the next sections.

## Adding a terms from an already used ontology

When you identified the term you want to add in an ontology that already is used by the eNanoMapper
ontology (see [this list](#A collection on ontology parts)), you basically need to identify
the following information:

1. what is the IRI of the term?
2. is it just that single term, or also also parent or child terms?
3. where in the eNanoMapper ontology should your selection show up?

### An example of adding a term and all children

The following screenshot shows a
[commit](https://github.com/enanomapper/ontologies/commit/e5f2d4812ce5f207792ffa22291705fbe44c6aad)
that adds a terms (*protein part*) from an ontology that already is used (SIO):

![Example commit that adds a term from an already used ontology.](Screenshot_20180325_165352.png)

## Adding a terms from an ontology that is not yet used


# Monitoring the building

## Checking the building

We use [Jenkins](https://jenkins.io/) as continuous build server, hosted at https://jenm.bigcat.maastrichtuniversity.nl/
(by [Maastricht University](https://www.maastrichtuniversity.nl/)). Here, jobs run for each included ontology:

* [AOP](https://jenm.bigcat.maastrichtuniversity.nl/job/AOP/)
* [BAO](https://jenm.bigcat.maastrichtuniversity.nl/job/BAO/)
* [BFO](https://jenm.bigcat.maastrichtuniversity.nl/job/BFO/)
* [CCONT](https://jenm.bigcat.maastrichtuniversity.nl/job/CCONT/)
* [CHEBI](https://jenm.bigcat.maastrichtuniversity.nl/job/CHEBI/)
* [CHEMINF](https://jenm.bigcat.maastrichtuniversity.nl/job/CHEMINF/)
* [CHMO](https://jenm.bigcat.maastrichtuniversity.nl/job/CHMO/)
* [EFO](https://jenm.bigcat.maastrichtuniversity.nl/job/EFO/)
* [ENVO](https://jenm.bigcat.maastrichtuniversity.nl/job/ENVO/)
* [FABIO](https://jenm.bigcat.maastrichtuniversity.nl/job/FABIO/)
* [GO](https://jenm.bigcat.maastrichtuniversity.nl/job/GO/)
* [HUPSON](https://jenm.bigcat.maastrichtuniversity.nl/job/HUPSON/)
* [IAO](https://jenm.bigcat.maastrichtuniversity.nl/job/IAO/)
* [NCIT](https://jenm.bigcat.maastrichtuniversity.nl/job/NCIT/)
* [NPO](https://jenm.bigcat.maastrichtuniversity.nl/job/NPO/)
* [OAE](https://jenm.bigcat.maastrichtuniversity.nl/job/OAE/)
* [OBCS](https://jenm.bigcat.maastrichtuniversity.nl/job/OBCS/)
* [OBI](https://jenm.bigcat.maastrichtuniversity.nl/job/OBI/)
* [PATO](https://jenm.bigcat.maastrichtuniversity.nl/job/PATO/)
* [SIO](https://jenm.bigcat.maastrichtuniversity.nl/job/SIO/)
* [UO](https://jenm.bigcat.maastrichtuniversity.nl/job/UO/)

## Checking the outcome

The final check to be performed, is to see if the term actually shows up on the ontology browsers (BioPortal,
Ontology Lookup Service, AberOWL, etc). For that, please check
[Browsing the eNM ontology with BioPortal, AberOWL and Protégé](BrowseOntology/Tutorial%20browsing%20eNM%20ontology.md) tutorial.

# Acknowledgments

This tutorial was written as part of the OpenRiskNet and NanoCommons projects.
[OpenRiskNet](https://openrisknet.org/) (Grant Agreement
[731075](http://cordis.europa.eu/projects/731075)) and
[NanoCommons](https://twitter.com/nanocommons) (Grant Agreement 
[731032](http://cordis.europa.eu/projects/731032)) are projects
funded by the European Commission within Horizon2020 Programme


