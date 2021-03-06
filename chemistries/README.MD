 # Chemistry definitions

**ALPHA version**
**The format, structure and names are all changing rather rapidly for development purposes. Feel free to have suggestions via PRs**

The purpose of this folder is to give centralized, open source easy access to people who want to automatically pull information relevant to a sequencing protocol.

This folder contains all the data necessary for chemistry definitions.

## Adapters

The adapters folder contains fasta files used in the different protocols. They are also linked in the `definitions.json` file.

## Whitelists

The whitelists folder contains the list of barcodes used in the protocols defined in the `definitions.json` file.

## Definitions

The `definitions.json` file holds the information relevant to all the chemistries defined here.
The main purpose of the file is to allow fast, consistente access to similar information accross protocols from one source.

If you want to add your chemistry, please follow those guidelines:

Here is a template for a new entry:

```
    "shortname":{
        "Description": "",
        "adapters": [],
        "whitelist": "",
        "barcode_structure_indexes": {
            "cell_barcode":{
                "R1":{
                    "start":,
                    "stop":
                },
            "umi_barcode":{
                "R1":{
                    "start":,
                    "stop":
                }
            }
        },
        "barcode_structure_string": {
            "R1": ""
        },
        "html": ""
    }
```

* shortname: is the key that is used to call the definition on the json file. The format is defined as follows: "contraction of compagny name" + "product name" + "version and/or specifics". Example: 10xchromiumFBV3 for "10x genomics" + "chromium" + "Feature barcoding V3"
* Description is a free field for a longer name of the protocol
* adapters is a list of paths pointing towards the adapters used in this protocol. The paths are relative to the folder containing the `definitions.json`
* whitelist is a path towards the whitelisted barcode list of the protocol. The path is relative to the folder containing the `definitions.json`
* barcode_structure_indexes defines the start and stop positions of the cell barcode and the umi barcode using numerical values. **Index starts at 1**
* barcode_structure_string defines the start and stop positions of the cell barcode and the umi barcode using a string. `C` defines a cell barcode,  `U` defines a UMI, `N` defines a random base.
* html is a path towards the html document of the protocol. The path is relative to the folder containing the `definitions.json`

