# Transfer Title Ownership with CrossRef

This is about what to do when AUP acquires a new title, for example a journal. There are two scenarios

1. AUP acquires _all_ of the disposing publisher's titles
2. AUP acquires _one_ of the disposing publisher's titles

This page is about scenario 2: how to let [CrossRef](crossref.md) know that the title now has a new owner, so that the DOI registration is handled succesfully and there are no [problems](doiregistrationproblems.md).

## how it works

- Crossref updates the title record to associate the title with the acquiring publisher’s prefix going forward
- content published _before_ the cut-off date keeps the _existing_ prefix and hence DOI
- content published _after_ the cut-off data gets the acquiring member’s prefix and hence DOI

## what we should do

1. Disposing and acquiring publisher confirm that all existing DOIs have definitely been registered with Crossref and agree financial arrangement for registration of DOIs.
2. Disposing or acquiring publisher contacts the [Crossref support team](https://www.crossref.org/contact/) to request a title transfer
3. Crossref updates the title record in our system and confirm when this is complete.
4. The acquiring publisher updates the metadata on existing DOIs as required.

## contacting CrossRef
There are two ways to request a title transfer

1. Post a title transfer to the [Enhanced Transfer Alerting Service (ETAS)](https://journaltransfer.issn.org/). This is Crossref's preferred option but it [seems](https://journaltransfer.issn.org/api?query=rpcn:aup) AUP doesn't do this.
2. [send Crossref confirmation](mailto:member@crossref.org) that the disposing publisher is aware of and agrees with the ownership transfer. The confirmation may be a forwarded email from the disposing publisher to the acquiring publisher acknowledging the transfer. The forwarded email must contain the original sender details.An announcement on the website of the disposing publisher works too.

Please be specific about what is being transferred - include ISSNs, ISBNs, and when you need the transfer to occur (if applicable). Do be specific about which prefix the title is being transferred to, as some publishers have more than one prefix. Let us know if this is a transfer of the entire title and all associated DOIs, or just a transfer for future content.

(NB: We used to allow disposing publishers to transfer titles themselves through the Metadata Manager tool, but this service has been deprecated).

## a journal can have multiple prefixes
If a single title is transferred, that title will have DOIs with at least two _different_ DOI prefixes: the one of the disposing publisher for all content published during that publisher's ownership, and the prefix of the acquiring publisher, for all content published after the moment of acquisition.

- Crossref holds "title records" in their sysem. The title record ties the title to the prefix belonging to the publisher (= a "member" of CrossRef).
- When the first DOI for a title is registered with CrossRef, this creates a title record in the Crossref system
- The publisher who owns the prefix is the only one allowed to create new DOIs for content belonging to that title (or update metadata on existing DOIs)
- if a title is acquired by another publisher with a different prefix, the DOIs of content published _before_ the acquisition _stay the same_
- DOIs of content published _after_ the acquisition _get the acquiring publisher's prefix_ and hence DOI
-the whole point of title ownership transfer is that the acquiring publisher gets to create new DOIs for that title (and gets to update metadata if necessary)

## some practical points
- check that all DOIs of content published before the acquisition is successfully registered with Crossref
- be as specific as possible when requesting a title transfer with Crossref (title, ISSNs, DOIs, etc.)
- using the disposing publisher's prefix have definitely been  us. 
- do _not_ register new DOIs (and/or DOIs with the new prefix) for content published before the acquisition. use the existing DOIs.


## quick summary
1. post a title transfer to ETA
2. alternatively, send a title transfer notification to CrossRef
3. make sure all DOIs (of the title) of the disposing publisher are registrered with CrossRef

Rembemr, the above only applies if one title is transferred. If _all_ titles are aquired, the disposing publisher's prefix is transferred over to the acquiring publisher.

## see also

- [Transferring responsibility for titles and DOIs](https://www.crossref.org/documentation/register-maintain-records/creating-and-managing-dois/transferring-responsibility-for-dois/)
- [Before, during, and after - a journey through title transfers](https://www.crossref.org/blog/before-during-and-after-a-journey-through-title-transfers/)
- [Transfer Alerting Service](https://journaltransfer.issn.org/)
- [The NISO Transfer Code of Practice](https://www.niso.org/standards-committees/transfer)



