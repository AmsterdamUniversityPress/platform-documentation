# Imprints

AUP Online supports imprints. That is to say that on Edify, which uses the term "publishers",

- there is an overview page of publishers: `/content/publishers` This pages lists all publishers on the platform.
- there are pages for publishers, e.g. `/content/p010` On this page, information about the publisher can be displayed, as well as its publications
- there is a search filter for publishers, e.g. `/search?value1=peanut&option1=fulltext&facetOptions=51&value51=%22p010%22&facetNames=pub_publisherIdent_facet&option51=pub_publisherIdent_facet&operator51=AND` which searches for the term `peanut` then fiters by a particular publisher.

## how to add a new publisher?

1. log-in as site admin
2. go to `/content/publishers`
3. click on the edit menu on the left-hand side (wrench symbol) and select `Create new Publisher`
4. Fill in the desired fields in the pop-up menu and click on `Create` in the bottom right corner.

You will see that the publisher URL corresponds to the publisher ID you entered. You can now edit the page to provide information about the imprint.

<!-- It's all HTML so you can do `<strong>Hanu</strong> <span style="color: rgb(209, 72, 65);">Publisher 1</span>` -->

## how to add publications to a publisher?

Add the publisher ID to the XML. 

```xml
<publisher>
  <publisher-name>Peanut Butter Publishers</publisher-name>
  <publisher-name specific-use="publisher-id">p010</publisher-name>
  <publisher-loc>
  <addr-line>Wall Street 1</addr-line>
  <postal-code>1018 VR</postal-code>
  <city>New York City</city>
  <country>USA</country>
  </publisher-loc>
</publisher>
```

The match with the publisher hinges on the publisher ID, so make sure you get that correct.

Ingenta tells us that adding publications to a publisher can also be done manually, by Ingenta. Do this only wehen there is a good reason not to follow the usual loading procedure. 

It is _not_ possible to "change" a product's publisher after it has been published on AUP Online. This means you have to assign it a publisher at publication time. The only way around this is to ask Ingenta to do it manually. Do this in emergencies only.

## adding a journal
If you're adding a new journal rather than adding books (or adding articles to an existing journal), do as follows:

1. Login as site admin
2. Go to the publisher page (or create a new one if it doesn't exist yet)
3. Create the journal. This associates the journal with the publisher

The publisher name is displayed on the journal homepage and article homepage for example. The journals listing page shows a publisher facet.

<!-- I had this working at one stage: https://qa.aup-online.com/content/content/test_pub1 is an example of a publisher and the journal _Scheepshistorie_ has been associated with it. But this page is gone now. -->

## see also

- the relevant change request is [CR009](https://confluence.ingenta.com/confluence/display/AUP/AUP+CR009+-+Add+imprints+functionality)
- the CR was delivered in the [2023 Q2 release](https://confluence.ingenta.com/confluence/display/AUP/AUP+Q2+2023+Release+Notes)
- although in fact it wasn't and is now in the [2024 Q4 release](https://confluence.ingenta.com/confluence/display/AUP/AUP+Q4+2024+Release+Notes)



