# ETYS data

## About
This related to the ETYS Spatial Demand data. After the data has been dowloaded/saved, transforming it ready for use in the regional fes visualisation is fully automated.

## Process
You first need to collate the inputs in the Inputs folder.

| Filename   | From spreadsheet | From SAS script/Python Notebook            |
| ---------- | ---------------- | -------------------------- |
| active.csv | Active worksheet | Write_ETYS-Demands-CSV.sas |
| dg.csv     | DG worksheet     | SAS_scripts.ipynb (calc_dgsplits function)         |
| sub1MW.csv | sub1MW worksheet | SAS_scripts.ipynb (calc_microsplits function)      |
| DSR.csv    | DSR worksheet    | Write_ETYS-Demands-CSV.sas                          |

Next open and run the python notebook Read-ETYS-Spatial.ipynb. This automatically creates all the output CSVs ready for the regional fes visualisation.

The python code includes a step that combines some of the GSPs together. This is because the areas that we have mapped (2019 GSPs) were not able to seperate out distinctive regions for all GSPs.
