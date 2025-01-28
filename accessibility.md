# Accessibility

## what is it?
Web accessibility means that websites, tools, and technologies are designed and developed so that people with disabilities can use them. 

- [W3C Accessibility Fundamentals Overview](https://www.w3.org/WAI/fundamentals/)

## standards
Several standards for accessibility of digital content, products, and services exist:

### 1. WCAG (Web Content Accessibility Guidelines)
The global standard for making web content accessible to people with disabilities, published by the W3C.

- Latest Version: WCAG 2.1 (2018); WCAG 2.2 (expected 2024); WCAG 3.0 (under development).
- Core Principles (POUR):
  - Perceivable: Content must be visible and usable with assistive technologies (e.g., text alternatives for images).
  - Operable: Interfaces must be navigable using a keyboard or other assistive inputs.
  - Understandable: Content and interface behavior must be predictable and clear.
   - Robust: Content must work with a variety of tools, including screen readers.
- Levels of Conformance: A (minimum), AA (recommended), AAA (highest).
- ISO/IEC 40500 is the **ISO standard** for WCAG 2.0. Its purpose is to provide international recognition and alignment of WCAG as a formal accessibility standard.
- Documentation: [WCAG 2 Overview](https://www.w3.org/WAI/standards-guidelines/wcag/)

### 2. EN 301 549
The European standard for ICT (Information and Communication Technology) accessibility, harmonized with WCAG 2.1.

- Focus: Broader than WCAG, covering software, hardware, websites, and mobile applications.
- Purpose: Required for public procurement in the EU under the EEA.
- [Documentation](https://www.etsi.org/deliver/etsi_en/301500_301599/301549/03.02.01_60/en_301549v030201p.pdf)

### 3. EPUB Accessibility Specification
A standard for making EPUB e-books accessible. Based on WCAG 2.1. Key Features:

- Text alternatives for images.
- Proper navigation (e.g., table of contents, landmarks).
- Accessibility metadata to indicate conformance.
- [EPUB Accessibility 1.1](https://www.w3.org/publishing/epub3/#bib-epub-a11y-11) is the accessibility specification for EPUB3

### 4. Section 508 (U.S.)
U.S. federal accessibility standard for ICT, aligned with WCAG 2.0. Key Areas:

- Electronic documents.
- Software and hardware interfaces.
- Websites and multimedia.
- Applicability: Primarily for federal agencies, but widely adopted in the private sector.
- [Documentation](https://www.section508.gov/)

### 5. ARIA (Accessible Rich Internet Applications)
A W3C technical specification to enhance web accessibility, especially for dynamic content.

- Focus: Provides roles, properties, and states to make web applications accessible (e.g., screen-reader-friendly dropdown menus).
- Best Practice: Use ARIA only when native HTML elements cannot achieve accessibility goals.
- [Documentation](https://www.w3.org/TR/wai-aria-1.1/)

### 6. PDF/UA-1 (Universal Accessibility)
UA stands for _universally accessibility_. This is a subtype of PDF/1.7, meant to comply with WCAG2. Key Features:

- Tagged content for reading order.
- Descriptive text for images and tables.
- Structured navigation (e.g., bookmarks).
- [ISO standard for accessible PDFs (ISO 14289-1:2014)](https://www.iso.org/standard/64599.html)

<!--
### 7. ADA (Americans with Disabilities Act) Standards
U.S. law requiring accessibility for public spaces, including digital environments. Legal Basis: While not a specific technical standard, WCAG is often used as the benchmark for compliance.

### 8. BITV (Germany)
The German federal standard for web accessibility. Based on WCAG 2.1, with specific national adaptations.

### 9. ATAG (Authoring Tool Accessibility Guidelines)
A W3C standard for making content creation tools accessible. Goals:
- Ensure tools can be used by people with disabilities.
- Ensure tools help authors create accessible content.
-->

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

https://jats.nlm.nih.gov/archiving/tag-library/1.4/element/alt-text.html

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
- `@xml-lang`

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
