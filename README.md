# Record-Linkage

Training a ML model to be able to link companies based on their names and certain other data points
Uses the RecordLinkage package to generate potential links and feature similarity data

Originally was used just to connect the Real Living Wage data to the ImpactScore database, we are now working on a more general model

## RLW1.0 

Trains a model by generated labeled candidate links using the Basic Company Dataset available from companies house, and Company Tax Data.

Used featureset:
- Normalised Copmany Name similarity
- Address Similarity
- Town Similarity
- County Similarity
- Postocode Exact

### Results:

Tested on across various models (in models folder):

Generally have high precision, but low recall scores. fscores around 60%

60% is not good enough but has proivided a base level. Later models will test different feature sets, and the model will update through further use.

It's also worth noting that the candidate links are generated through the RecordLinkage Package, and so all candidate links are somewhat similar.


confusion matrix
[[1276 1605]
 [ 284 3342]]
fscore 0.5746453501463635
recall 0.44290177021867405
precision 0.8179487179487179

## General-RL 1.0

This is ongoing, and data is being prepared to train the model atm. Candidate Links have been generated, and are being labelled for testing.

Current Featureset being Tested:

- CompanyNumber SIM
- RegAddress#AddressLine1 SIM 
- RegAddress#AddressLine2 SIM
- RegAddress#PostTown EXACT 
- RegAddress#County EXACT
- RegAddress#PostCode EXACT
