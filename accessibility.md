# Accessibility

## what is it?
Web accessibility means that websites, tools, and technologies are designed and developed so that people with disabilities can use them. 

- [W3C Accessibility Fundamentals Overview](https://www.w3.org/WAI/fundamentals/)

## standards
Several standards exist...

##  EAA
The European Accessibility Act (EAA), set to be fully implemented by mid-2025, requires digital content, including scientific publications and digital books, to be accessible to individuals with disabilities. 

The act can be found [here](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32019L0882).

## what does this mean for the platform?
Does the platform meet global accessibility standards? The Librarians' FAQ says

> We have aimed for WCAG 2.0 AA compliance with the Web Accessibility Initiative recommendations (WAI) and compliance with Section 508 Amendment to the Rehabilitation Act of 1973.

But...
- there is no accessibility page or statement
- there is no VPAT

See also
- [VPAT on Wikipedia](https://en.wikipedia.org/wiki/Voluntary_Product_Accessibility_Template)
- [VPAT on ITIC](https://www.itic.org/policy/accessibility/vpat/)

## what does this mean for the content?
Let's answers this in terms of formats:

- PDF
- JATS/BITS XML

## PDF
...


## JATS / BITS XML
EAA has implications for markup languages like JATS (and BITS), which are widely used in the publishing industry for scholarly articles and books.

The JATS used at AUP has to comply with the four principles of accessibility of websites and mobile applications refered to by EAA:

1. Perceivable information and user interface components: Text alternatives for non-text content (e.g., images, tables). Logical structure for content (headings, lists, etc.).
2. Operable interface: Navigation and interaction through structural tagging (e.g., `<sec>`, `<p>`).
3. Understandable content and interface: Clear labeling and hierarchical structure. Descriptive metadata.
4. Robustness: Compatibility with assistive technologies (e.g., screen readers) and other user agents

<!--
1. perceivability, meaning that information and user interface components must be presentable to users in ways they
can perceive;
2. operability, meaning that user interface components and navigation must be operable;
3. understandability, meaning that information and the operation of the user interface must be understandable;
4. robustness, meaning that content must be robust enough to be interpreted reliably by a wide variety of user agents, including assistive technologies.
-->

### Key JATS/BITS Elements and Attributes for Accessibility

#### 1. Structural Elements
These ensure the logical organization of content, improving navigation:

- `<article>` (JATS) / `<book>` (BITS): Top-level containers for the document.
- `<front>`, `<body>`, `<back>`: High-level structural divisions.
- `<sec>`: Defines sections within the content, supporting hierarchical navigation.
- `<title>` and `<subtitle>`: Used for headings and subheadings.
- `<p>`: Paragraphs.
- `<list>` and `<list-item>`: Structured lists.
- `<table-wrap>` and `<table>`: For data tables, with accessibility requirements for captions and column headers.

#### 2. Text Alternatives
Ensure all non-text content is described:

- `<alt-text>`: Provides a textual description of images, figures, and other visual elements.
- `<long-desc>`: Used for extended descriptions of complex images, graphs, or charts.
- `<caption>`: Short description for figures and tables.

#### 3. Semantics and Metadata
Provide additional context for better comprehension:

- `<article-title>` / `<book-title>`: Primary titles.
- `<contrib>`: Specifies authors and contributors.
- `<abstract>`: Gives a summary of the content.
- `<kwd-group>`: Keywords for enhanced discoverability.
- `<doi>` and `<uri>`: Persistent identifiers to ensure reference integrity.

#### 4. Accessibility Attributes
Attributes in JATS/BITS that enhance accessibility:

- `@id`: Unique identifiers for internal linking.
- `@xlink:href`: Links to external resources or internal references.
- `@alt`: Brief alternative text for figures and images.
- `@role`: Specifies the purpose of elements (e.g., @role="doc-chapter").

#### 5. Tables
Accessible tables require:

- `<thead>` and `<tbody>`: Logical separation of header and body rows.
- `<th>` and `<td>`: Column headers and data cells, with @scope or @headers attributes for accessibility.
- `<summary>`: Provides a concise description of the table.

### example

```xml
<fig id="fg-3">
 <caption>
  <p>Picture with a Positive Association</p>
 </caption>
 <graphic xlink:href="frontView.png">
  <alt-text>Collie puppy image</alt-text>
 </graphic>
</fig>
```

```xml
<fig id="fig1">
<label>Diagram 1.</label>
<caption><title>Kwantitatief overzicht nominale kernen</title></caption>
<graphic xlink:href="QUE2022.1.001.KLEI_fig1.jpg"/>
</fig>
```

- why is title used instead of p?
- what is the function of label?
- 
  
## see also
Search Confluence [here](https://confluence.ingenta.com/confluence/dosearchsite.action?cql=siteSearch+~+%22accessibility%22&queryString=accessibility).
