# Validation

This is about checking if your XML is ok. XML is ok if it is

1. well-formed, i.e. if all opening tags have closing, and if all the correct pointy brackets (`<`, `>`) are there
2. valid, i.e. if the XML satisfies the XML schema. An XML Schema describes the structure of an XML document

All checkers that can check validty can also check well-formedness. The opposite is not necessarily true. Many of the online checkers, for example, only check well-formedness. This makes them useless for us, because we need to know if our XML is correct JATS or BITS. For that reason, this page is about validity checking.

## how to check the validy of your XML document?

The best answer is: buy a decent XML editor like Oxygen. This has a well-formedness and validity button. Press it and do whatever the messages that pop up tell you. 

You may be able to do the same with other XML editors. (There are many). However, I was unable to do so with VS Code, even after installing the official XML plug-in. Or rather, VS Code validates against the schema, but it puts certain requirement on it, and when the schema doesn't meet these, VS Code reports errors and does not properly validate.

So here is a different approach.

## First, basics

Schemas come in three forms:

1. XML Schema (with  uppercase S!). These documents are written in the powerful XML Schema language or XML Schema Definition (XSD)
2. RELAX NG. These documents are written in the simpler REgular LAnguage for XML Next Generation (RNG)
3. DTD. This stands for document type definition. It is the oldest schema and part of the original XML specifications

How to connect your XML document with a schema? Refer to the schema in your DOCTYPE elelement at the top of your XML document. This example refers an online version of one of the JATS DTDs:

```xml
<!DOCTYPE article PUBLIC "-//NLM//DTD JATS (NISO Z39.96-2019) Journal Publishing DTD v1.2 20190208//EN" "JATS-journalpublishing1-mathml.dtd"> 
```

This example refers a _local_ version of one of the JATS DTDs. This menas it is stored on your computer:

```xml
<!DOCTYPE article PUBLIC "-//NLM//DTD JATS (NISO Z39.96-2019) Journal Publishing DTD v1.2 20190208//EN" "../JATS-Publishing-1-2-MathML3-DTD/JATS-journalpublishing1-mathml.dtd"> 
```

Make sure to use the correct path! It can be absolute or relative. 

## validating
Take the following steps:

1. download the schema _and all accompanying files_ from the [[NLM site](https://jats.nlm.nih.gov/publishing/tag-library/1.2/chapter/which-dtd.html)
2. Go into the folder with all of the files. You will see several DTDs. Open `mathml3.dtd` and go to the very bottom of the document. Look for these lines:

```xml
<!ATTLIST %semantics.qname;
  %CommonAtt;
  %DefEncAtt;
  cd CDATA #IMPLIED
  name CDATA #IMPLIED> [
  <!ENTITY NS.prefixed "entity-value">
] [
  <!ENTITY NS.prefixed "entity-value">
]
```

Replace them with these lines:

```xml
<!ATTLIST %semantics.qname;
  %CommonAtt;
  %DefEncAtt;
  cd CDATA #IMPLIED
  name CDATA #IMPLIED
>

<!ENTITY % NS.prefixed "INCLUDE">
<![%NS.prefixed;[
  <!ENTITY NS.prefixed "entity-value">
]]>

```

Save and close.
3. make sure to have `xmllint` installed. It comes pre-installed on MacOS. See [the official site](https://gitlab.gnome.org/GNOME/libxml2/-/wikis/home) for how to get it.
4. Open a terminal (command line) in the folder where your XML document is situated and type the following

```ls
xmllint --noout --dtdvalid PATHTOYOURDTD YOURXMLFILE
```

For example, 
```ls
xmllint --noout --dtdvalid ../JATS-Publishing-1-2-MathML3-DTD/JATS-journalpublishing1-mathml.dtd QUE2022.1.001.KLEI.xml
```

This should now validate your document. if there are any errors, you should see error messages in the terminal. Happy debugging 🐞🐞🐞 
