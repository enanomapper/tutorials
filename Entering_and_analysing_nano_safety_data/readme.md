---
layout: default

trainingMaterial:
  "@context": http://schema.org/
  "@type": CreativeWork
  "@id": https://enanomapper.github.io/tutorials/Entering_and_analysing_nano_safety_data/
  description: "Tutorial that covers various aspects of working with the eNanoMapper database. It discussed searching, adding, and downloading data from an eNanoMapper database."
  "http://purl.org/dc/terms/conformsTo":
    - "@id": "https://bioschemas.org/profiles/TrainingMaterial/1.0-RELEASE"
      "@type": "CreativeWork"
  audience:
    - "@type": Audience
      name: PhD students
    - "@type": Audience
      name: post-docs
    - "@type": Audience
      name: Bioinformatician
  genre:
    - http://edamontology.org/topic_0089
    - http://edamontology.org/topic_3070
    - http://edamontology.org/topic_3314
    - http://edamontology.org/topic_0091
    - http://edamontology.org/topic_2258
  name: Entering and analysing nano safety data
  author:
    - "@type": Person
      name: Egon Willighagen
      identifier: 0000-0001-7542-0286
    - "@type": Person
      name: Nina Jeliazkova
      identifier: 0000-0002-4322-6179
  educationalLevel: Intermediate
  keywords: ontologies, enanomapper
  license: CC-BY 4.0
  url: https://enanomapper.github.io/tutorials/Entering_and_analysing_nano_safety_data/readme.html
  version: 1.0.3
---

# Entering and analysing nano safety data

* Author: Nina Jeliazkova, Egon Willighagen
* License: CC-BY 4.0
* Version 1.0.3

## Introduction

The goal of this workshop is to make the participants familiar with the eNanoMapper solutions for
data management and data access. We will demonstrate how the
[http://data.enanomapper.net/](http://data.enanomapper.net/) integrates
various data sets, how you can search for materials, how you can upload data, and how we can use the
application programming interface (API) to access data. This document provides information how to
run the exercises. For detailed description of the eNanoMapper data solutions, please consider
the publication doi:[10.3762/bjnano.6.165](https://doi.org/10.3762/bjnano.6.165) and resources at
[http://enanomapper.net/](http://enanomapper.net/).

* [Searching](searching.md) (HTML)
* [Download data from within R](downloading.md) (HTML)
* [Data preparation & Upload](uploading.md) (HTML)
* [Data visualization](visualisation.md) (HTML)
