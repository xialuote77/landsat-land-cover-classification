# Manual reproduction guide

The original work used ENVI. This repository preserves evidence and method documentation; it is not an executable pipeline.

1. Recover the original Landsat 8 scene metadata, multispectral bands and acquisition details from the authorised course source. The original product ID/date and processing-level details are not established by the retained figures. An arbitrary new scene would be a new experiment.
2. Recover the original training/test ROI files and ENVI configuration. These are not bundled here. Without them, the published accuracy cannot be reproduced exactly.
3. Open the metadata file, verify band identities, projection, pixel size, processing level and no-data mask. Confirm the physical meaning of input values before computing indices. Document any scaling/offset needed by that product; the report does not establish that this was done.
4. Inspect true-colour and false-colour composites and apply display stretching. Do not confuse display enhancement with radiometric calibration.
5. Recreate the documented band ratios and NDVI=(B5-B4)/(B5+B4), handling no-data and zero denominators explicitly. Recover rather than guess the original spectral preprocessing.
6. Restore the six class ROIs and verify separation of training and test areas. Restore the exact multispectral input list and maximum-likelihood settings, then classify.
7. Evaluate on the original test ROIs, retain raw confusion counts, and calculate overall accuracy, Kappa and per-class producer/user accuracy. Add spatially independent validation for a new portfolio extension.

No raw scene, ROI geometry, executable ENVI batch file or original project is supplied. The listed steps describe the workflow and missing dependencies; they do not establish successful reproduction.
