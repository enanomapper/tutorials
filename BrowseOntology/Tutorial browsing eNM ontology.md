
Browsing the eNM ontology with BioPortal, AberOWL and Protégé
=============================================================

* Release: 2017-11-19
* Version: v1.1
* Main Author: Linda Rieswijk
* Authors: Linda Rieswijk, Friederike Ehrhart, and Egon Willighagen
* License: Creative Commons Attribution (CC-BY) 4.0

Introduction
------------

The field of engineered nanomaterials is exponentially growing as well as the demand to assure the
safe use of this type of materials. Nanomaterials are defined as being materials with at least one
external dimension in the size range from approximately 1-100 nm. Nanoparticles are objects with
all three external dimensions at the nanoscale. Engineered nanomaterials can be used within a
numerous amount of application such as:

1. In the design of pharmaceuticals specifically targeting organs or cells in the body such as cancer cells which also enhances the effectiveness of therapies.
1. To make materials such as cloth or cement stronger and lighter.
1. Use in electronics, as environmental remediation or clean-up to bind with and neutralize toxins, for their anti-bacterial function in cosmetics etc.  

The primary objective of WP2 within the FP7 EU-funded eNanoMapper (eNM) project is to develop and
disseminate a comprehensive ontology for the nanosafety domain, encompassing nanomaterials and all
information relating to their characterization, as well as information describing relevant
experimental paradigms, biological interactions, safety indications and experimental paradigms.

The current version of the eNanoMapper ontology is based on the re-usage of 18 existing ontologies
(e.g. NanoParticle Ontology, BioAssay Ontology, Experimental Factor Ontology) together with
specialized engineered nanomaterials and nanotechnology vocabularies and definitions, which have
been described by several national and international standardization committees (e.g.
International Organization for Standardization, Joint Research Centre).

The re-used ontologies (OWL file) were made slimmer, if necessary modified using the free,
open-source ontology editor Protégé5 and new terms were added using the Issue Tracker within GitHub.

The eNM ontology might be accessed through three different ways, namely online via BioPortal and
AberOWL or locally using the open-source Protégé software. This tutorial focusses on browsing
through the eNM ontology when one would be interested in finding a Unique Resource Identifier (URI)
for mapping a term originating from for example a database schema. Using URIs for database schemas
will facilitate the harmonization of data originating from different sources and will make them
more comparable. 

In order to generate an ontology for engineered nanomaterials which is covering all domains also
instructions are provided within this tutorial on which steps should be taken when a term is not
present within the eNM ontology. 

Tutorial for usage of the eNanoMapper Ontology for mapping terms
----------------------------------------------------------------

There are three options for searching URIs for terms originating from for example a database
schema within the eNM ontology.

### eNM ontology with BioPortal

* Go to the ENM ontology within BioPortal.
.* http://bioportal.bioontology.org/ontologies/ENM
* If you click on “classes” you will find the hierarchical ontological tree.
* By clicking on “entity” all the sub- and head classes will be provided.
* In the box of “Jump To:” a particular term might be searched within the ontology.
* In this example we are interested in “zeta potential”.
* Suggestions for possible URIs will be given which are present within the eNM ontology.
* Click on the term you are interested in (in this case “zeta potential”).
* Details will be provided on the term and the position of the term in the hierarchical ontological tree will be visualized (see Figure 1).

![Screenshot of BioPortal](fig1.png)
Figure 1: Browsing the eNM ontology within BioPortal.

### eNM ontology in AberOWL

* Go to the ENM ontology within AberOWL.
.* http://aber-owl.net/ontology/ENM/
* On the left you will find an interactive view of the hierarchical ontological tree.
* If you click on “entity” the tree will be unfolded thereby revealing the sub- and head classes of the ontology.
* Above the “entity” field you will find a search box in which terms may be typed.
* In this case we are interested in finding “zeta potential”.
* Suggestions will be given for potential URIs which are present in the eNM ontology.
* If you click on one of the suggested URIs the hierarchical ontological tree will fold out.
* On the right the following information is given for this particular URI within the eNM ontology, for example for “zeta potential” (See Figure 2).

![Screenshot of AberOWL](fig2.png)
Figure 2: Browsing the eNM ontology using AberOWL.

### Open and browse the eNM ontology within Protégé

* Protege can be downloaded from this page:
.* http://protege.stanford.edu/
* Download the chosen ontology as .owl file from BioPortal (in this case the eNM ontology → See Figure 3).

![Screenshot of BioPortal for downloading the OWL file](fig3.png)
Figure 3: The OWL file from the eNM ontology on BioPortal.

* Open Protégé and go to “file” “open” and select the downloaded .owl file - alternatively, “open from URL” and enter the URL.
* Open the tab “entities” to get to the terms.
* In this case we are interested in finding “amphiphilic”.
* In class annotations and class usage you will find the detailed information: label, code, preferred name, synonym which can be edited, deleted or annotated (See Figure 4).

![Screenshot of Protégé](fig4.png)
Figure 4: Browsing the eNM ontology in Protégé.

### Follow-up procedure if term is not present in the eNM ontology

* If the term is not present within the eNM Ontology it needs to be searched within one of the other existing ontologies.
* At the moment the following external ontology sources are used within the creation of the eNM ontology (total of 6690 classes) (See Figure 5 and 6).

