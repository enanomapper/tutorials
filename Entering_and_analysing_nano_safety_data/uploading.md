---
layout: default
---

# Data preparation & Upload

The next task will be about preparing data for upload into an eNanoMapper instance.  You will look at a template with data, compiled by the [MODENA](http://www.cost.eu/COST_Actions/mpns/TD1204) COST Action project, explore the content, and upload this template into the test eNanoMapper data server [https://apps.ideaconsult.net/enmtest](https://apps.ideaconsult.net/enmtest).

The following three  files are used in the exercise: 

![Three MODENA data sets.](media/image18.png)

* MODENA-EC50_EC25.xlsx contains physicochemical and biological characterisation of two nanomaterials. The data was extracted from the literature, compiled by the MODENA project and made publicly available after the end of the MODENA project.
* MODENA-modelling-pchem.json is a configuration file, describing which parts of the Excel file MODENA-EC50_EC25.xlsx contain the physicochemical readouts and metadata of the experiment
* MODENA-modelling-tox.json is a configuration file, describing which parts of the Excel file MODENA-EC50_EC25.xlsx contain the biological readouts and metadata of the experiments
* The configuration files are written in [JSON](http://www.json.org/), a lightweight data interchange format.

## The Test Data

Download the files from this folder:

Link missing, see [this issue](https://github.com/enanomapper/tutorials/issues/15).

## The Test Server

Go to [https://apps.ideaconsult.net/enmtest](https://apps.ideaconsult.net/enmtest). This is the test server for data upload. 

## The Upload Page

Use the menu to go to the upload page: `Data upload` > `Spreadsheet upload`.

![Screenshot of navigating the menu](media/image19.png)

The following upload page will appear:

![The actual upload page](media/image20.png)

## Using the web form for upload

* Click on the top *Choose File* button and select the `MODENA-EC5_EC25.xlsx` file.
* Click on the bottom *Choose File* button and select the `MODENA-modelling-pchem.json`
* Uncheck the *Clear existing study records*
* Uncheck the *Clear existing composition records*
* Click *Submit*

![The two places to provide the data file and the nmdataparser meta data](media/image21.png)

Clicking the *Submit* button starts the upload task, the following screen appears:

![After submitting the data, the may have to wait for the data to be processed...](media/image22.png)

On completion, the status page changes to *Ready. Results available*:

![...but at some point the loading is completed.](media/image23.png)

## View the uploaded materials

Clicking on the link will lead to the uploaded materials.
Alternatively, use the menu *Data collections* > *Nanomaterial contributors* to display the datasets.

![Navigating the menu...](media/image24.png)

* Look for the *Nanomaterial contributor name* ENM_WORKSHOP (*Hint: use the Filter function, marked in blue*). 
* Click on the substances link to explore the uploaded content (*marked in red*).

![ENM_WORKSHOP contributions...](media/image25.png)

The list of materials uploaded appears as shown in the next screenshot:

![List of nanomaterials just uploaded.](media/image26.png)

Each link in the columns *Substance name* leads to a detailed page with study details. Use the *Expand all* buttons to display and explore the results:

![Details for one of the uploaded nanomaterials.](media/image27.png)
    
## Upload MODENA biological characterisation data

Repeat the upload with the step 4.3. and MODENA-modelling-tox.json in order to upload biological characterisation data.
Note that this exercise uses predefined files and configurations with the goal to get you familiar with the process of data upload. This exercise does not include data preparation task, such exercise will be subject of subsequent tutorials and / or bilateral interaction between eNanoMapper and NSC projects. 

## Upload Dose Response Data

Download LDH assay data, generated by FP7 MARINA project (KI, [1]) from [https://github.com/enanomapper/tutorials/tree/master/Hackathon_on_templates_for_data_collection/upload/blocks](https://github.com/enanomapper/tutorials/tree/master/Hackathon_on_templates_for_data_collection/upload/blocks).

There are two files, `MARINA-invitro-WP09-P32-NM103TiO2-HMDM_Cytotoxity_LDH.xls` and `MARINA-invitro-config.json`. The Excel file is a typical format used in many NanoSafetyCluster projects, and consists of several worksheets.  Repeat the upload with the step 4.3. with these files.

1. L. Farcal, F. Torres Andón, L. Di Cristo, B. M. Rotoli, O. Bussolati, E. Bergamaschi, A. Mech, N. B. Hartmann, K. Rasmussen, J. Riego-Sintes, J. Ponti, A. Kinsner-Ovaskainen, F. Rossi, A. Oomen, P. Bos, R. Chen, R. Bai, C. Chen, L. Rocks, N. Fulton, B. Ross, G. Hutchison, L. Tran, S. Mues, R. Ossig, J. Schnekenburger, L. Campagnolo, L. Vecchione, A. Pietroiusti, and B. Fadeel, “Comprehensive In Vitro Toxicity Testing of a Panel of Representative Oxide Nanomaterials: First Steps towards an Intelligent Testing Strategy,” PLoS One, vol. 10, no. 5, p. e0127174, May 2015.

## Upload Data in JRC/NANoREG template (Advanced)

Download LDH template and the corresponding JSON configuration from
[https://github.com/enanomapper/tutorials/tree/master/Hackathon_on_templates_for_data_collection/upload/columns](https://github.com/enanomapper/tutorials/tree/master/Hackathon_on_templates_for_data_collection/upload/columns).

There are two files, `datatemplate_INVITRO_CYTOTOXICITY_LDH.xlsx` and `in_vitro_Cytotoxicity_LDH_sheet.json`. The Excel file is part of the eNanoMapper release of data entry templates, based on JRC/NANoREG templates. More information at [https://github.com/enanomapper/tutorials/tree/master/DataTemplates](https://github.com/enanomapper/tutorials/tree/master/DataTemplates).

In this exercise the template is (almost) empty and before upload the data has to be entered. You may use the data from the file in 4.6 or enter your own data.

Repeat the upload with the step 4.3. with these files.
