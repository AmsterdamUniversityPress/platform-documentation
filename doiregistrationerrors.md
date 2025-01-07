
# Problems in DOI registration with CrossRef

## context
The AUP Online platform handles the [DOI Registration](https://amsterdamuniversitypress.github.io/content-loading/doiregistration) for AUP content as part of its so-called "distribution" function. This means that an XML file with metadata is sent to a DOI registrar - CrossRef in this case. This "CrossRef" XML is produced by converting the JATS XML that is used to upload content to the platform. This JATS (or BITS) XML contains, among other information, the DOI created by the AUP typesetters. _Created_ - not yet registered.

Four possibilities now arise:
1. the CrossRef XML is valid and the DOI is registered. No notification is sent by CrossRef.
2. the CrossRef XML is not valid and the DOI is not registered. A notification is sent by CrossRef.
3. the CrossRef XML is valid and the DOI is registered. A notification (to the contrary) is sent by CrossRef.
4. the CrossRef XML is not valid and the DOI is not registered. No notification is sent by CrossRef.

Possibility three, a false negative, has never occured, as far as I know. Possibility four, a false positive, happens whenever a journal is not properly registered with the DOI registrar as belong to AUP. _Studia Rosenthalia_ is a recent example. Possibility one, a positive, is cause for joy. Possibility two, a negative, is the subject of what follows here.

## errors
Notifications with errors that occurred during the DOI registration arrive in the AUP Support email box every hour. 

What errors? A few examples of such notifications are attached for further study. A further few examples will be discussed here. Roughly speaking: the majority of errors is connected to the author:

1. Surname field contains information that should not be there
2. Affiliation is empty or contains too much information
3. ORCID is corrupt

These errors occur in front list and backlist content. It must be emphasised that they occur _very infrequently_, perhaps once in a few thousand cases. (I did not count them; perhaps I should).

Other sorts of errors are much more rare: corrupt DOIs, corrupt registrant,  missing volumes and issue numbers. They seem connected to content loaded in error, perhaps later corrected but with different file names, or to the early days of the platform when loading conventions weren't crystallised yet. They can therefore be ignored, except for the **urgent caution** that folder and file names must be correct and consistent. Inconsistencies lead to pollution of the loading pipeline and in some cases to broken pages or functionality. 

## a few examples

Example 1. GO2024.1.006.ENGE. Corrupt ORCID. On top the CrossRef XML as it is returned in the error message. Below the JATS.

![[example1-GO2024.1.006.ENGE-corruptorcid-jats.png]]

![[example1-GO2024.1.006.ENGE-corruptorcid-crossref-error.png]]

Example 2. TVA2024.4.005.COLL Missing authorname. On top the CrossRef XML as it is returned in the error message. Below the JATS.

![[example2-TVA2024.4.005.COLL-noauthname-jats.png]]

![[example2-TVA2024.4.005.COLL-noauthname-crossref-error.png]]

## schema
The CrossRef XML is validated again an online schema, http://www.crossref.org/schema/4.4.2. The schema - in this case, version 4.4.2 -  is referenced in the CrossRef XML:

```xml
<doi_batch xmlns="http://www.crossref.org/schema/4.4.2"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xmlns:xs="http://www.w3.org/2001/XMLSchema"
xmlns:pub="http://pub2web.metastore.ingenta.com/ns/"
xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
xmlns:prism="http://prismstandard.org/namespaces/1.2/basic/"
xmlns:dcterms="http://purl.org/dc/terms/"
xmlns:prism2="http://prismstandard.org/namespaces/2.0/basic/"
xmlns:fn="http://www.example.org/functions"
xmlns:fr="http://www.crossref.org/fundref.xsd"
version="4.4.2"
xsi:schemaLocation="http://www.crossref.org/schema/4.4.2 http://www.crossref.org/schema/deposit/crossref4.4.2.xsd">
<head xmlns:rel="http://www.crossref.org/relations.xsd"
xmlns:ai="http://www.crossref.org/AccessIndicators.xsd">
<doi_batch_id>amsterdamuniversitypress_2025_01_07_06_31_39</doi_batch_id>
<timestamp>202501070631390000</timestamp>
<depositor>
<depositor_name>Publishing Technology</depositor_name>
<email_address>pub2web-cdc-aup-live@ingenta.com</email_address>
</depositor>
<registrant>Amsterdam University Press
</registrant>
</head>
```

CrossRef has extensive documentation. Relevant links:

- https://www.crossref.org/documentation/schema-library/
- https://www.crossref.org/documentation/schema-library/metadata-deposit-schema-4-4-2/ 

The schema can be downloaded here: https://gitlab.com/crossref/schema/-/tree/master/schemas?ref_type=heads 

## fixes
How to fix this? Automated checks. Either before JATS is created, or during (Schematron), depending on the workflow.

1. Error 1 is tricky, but a check for number of characters and/or number of white spaces should make a good start
2. Allow no empty `<aff>` tag (or any other tag, for that matter) in the JATS/BITS. Even if it is valid according to the JATS schema. Also, check for number of characters in this field
3. Check against the ORCID API. ORCID has public and private APIs.

It should be emphasised once more that CrossRef does not check the JATS. This is not about the JATS. This is about the data _inside_ the JATS tags.

## see also
- [DOI Registration](https://amsterdamuniversitypress.github.io/content-loading/doiregistration)
