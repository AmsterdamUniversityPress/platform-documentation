# DOI Registration

The platform performs a task called [distribution](distribution.md). This means it sends metadata and content to specified third parties. The site admin can set this up. 

One distribution line set up is to CrossRef. It has at least two purposes: DOI registration and retrieval of [references](references.md). The latter are discussed elsewhere on these pages. This page deals with DOI registration.

First, it is good to know that DOIs can be created by anyone (as long as they comply with the specifications). Their _registration_ however, is in the hand of a few third parties, and CrossRef is undoubtedly the most prominent one. 

CrossRef makes sures the DOI resolves to a URL. To that end, the publisher has to submit metadata to CrossRef. (With that metadata, CrossRef performs a lot of other functions as well, like tracking references to content items in other content items).

This task is performed by [Edify](edify.md). The platform takes the metadata (in JATS or BITS XML), and transforms it into another type of XML that CrossRef can understand, and sends it to CrossRef. 

CrossRef then either registers the DOI, or returns an error message. 

These error message take the form of emails that are sent to the Support mailbox at AUP. (The site admin can choose where they are sent).

## procedure for dealing with error messages
There is currently no proper procedure for dealing with these error message. Error messages are sent - hourly! - by the platform to the AUP Support email inbox. 

I am currently clearing the backlog. Going forward both Crius and AUP staff need to be able to take action. See [here](doiregistrationerrors.md).

## submitting DOIs
DOIs are submitted in the form of an XML file containing metadata of the publication. Example below.

- https://gitlab.com/crossref/schema/-/blob/master/best-practice-examples/journal.article5.3.0.xml

## see also

- [DOI Registration Errors](https://amsterdamuniversitypress.github.io/platform-documentation/doiregistrationerrors)

