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
PDF-UA-1. See above.

<!--
Praktisch gebruik van PDF UA
Hoewel PDF/UA toegankelijkheid voor online publicatie mogelijk maakt, blijft terughoudendheid in het gebruik van pdf geboden.

PDF/UA biedt een normatieve en uitgebreide manier om pdf-inhoud te testen op conformiteit met WCAG 2.0. Als onderdeel van de ontwikkeling van de PDF/UA-norm werkten de leden van het comité, zoals Adobe, Microsoft, Appligent, Crawford Technologies en vele anderen, samen met de WCAG-commissie om WCAG 2.0-richtlijnen in kaart te brengen in de specifieke secties van de PDF/UA-standaard en daarmee de naleving van WCAG te regelen door het volgen van de precieze specificaties binnen de ISO-standaard.

Een pdf die voldoet aan de ISO 14289-1 (ook bekend als PDF/UA) -specificatie, is een beperkte vorm van Adobe PDF 1.7 (zoals gedefinieerd in ISO 32000-1) bedoeld om toegankelijkheid en ondersteuning te waarborgen voor ondersteunende technologie die wordt gebruikt door een persoon met een handicap.

Vereisten voor PDF / UA-conformiteit zijn consistent met de Web Content Accessibility Guidelines (WCAG) 2.0, een W3C-aanbeveling van 11 december 2008. De beperkingen op een PDF 1.7, voor PDF / UA-compliance, zijn de volgende:

Alle echte inhoud zal worden getagd. Artefacten worden niet getagd.
Inhoud zal gemarkeerd worden in de structuurboom met semantisch gepaste tags in een logische leesvolgorde. De standaard legt gedetailleerde gebruikseisen op voor koppen, tabellen en lijsten om navigatie door ondersteunende technologie te ondersteunen.
Alle structuurtypen die worden gebruikt, moeten standaard zijn of worden toegewezen aan de standaard.
Grafische objecten (afbeeldingen) die echte inhoud zijn, moeten een figuurlabel krijgen met alternatieve of vervangende tekst; bijschriften bijbehorende figuren moeten worden getagd als bijschriften.
Informatie mag niet worden weergegeven door contrast, kleur, indeling of lay-out, tenzij de inhoud is getagd om alle bedoelde betekenis weer te geven.
Alle informatie die met geluid wordt overgebracht, moet ook zonder geluid beschikbaar zijn.
Lettertypen moeten zijn ingesloten.
Dynamische XFA-formulieren zijn niet toegestaan. Statische XFA-formulieren kunnen worden gebruikt.
-->


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
- `@xml-lang`: Assistive technologies use the @xml:lang attribute to determine pronunciation rules, voice synthesis, and other language-specific behaviors.

#### 5. Tables
Accessible tables require:

- `<thead>` and `<tbody>`: Logical separation of header and body rows.
- `<th>` and `<td>`: Column headers and data cells, with @scope or @headers attributes for accessibility.
- `<summary>`: Provides a concise description of the table.

## example 1. Figures

### current XML (January 2025)
```xml
<fig id="fig1">
<label>Diagram 1.</label>
<caption><title>Kwantitatief overzicht nominale kernen</title></caption>
<graphic xlink:href="QUE2022.1.001.KLEI_fig1.jpg"/>
</fig>
```

<!--
#### questions
- why is title used instead of p?
- what is the function of label?
-->

Note the missing `@alt` attribute for `<graphic>`. Screen readers will not be able to describe the image. Also, `<label>` should not replace `<caption>`. Screen readers will not necessarily read the caption. Lastly, `@xml:lang` is missing for multilingual support.

### correct XML (in the light of EEA)
```xml
<fig id="fig1" xml:lang="nl">
  <caption>
    <title>Diagram 1: Kwantitatief overzicht nominale kernen</title>
  </caption>
  <graphic xlink:href="QUE2022.1.001.KLEI_fig1.jpg" alt="Diagram 1: Kwantitatief overzicht nominale kernen"/>
  <alt-text>Dit diagram toont een kwantitatieve analyse van nominale kernen, met een vergelijking van frequenties en patronen.</alt-text>
</fig>
```

#### Summary of fixes

- ✅ Added `alt` text for better screen reader support. Use `@alt` or `<alt-text>` if a longer explanation is ndded
- ✅ Moved the label into `<caption>` for proper structure.
- ✅ Specified `xml:lang="nl"` for correct pronunciation.
- ✅ Optional: `<long-desc>` for complex figures.

Of course, these fixes mean nothing if the HTML generated from the XML is not accessible...

#### `@alt` vs `<alt-text>`
Use `@alt` for **simple** alternative text
- short, concise descriptions (one-liners)
- place directly inside `<graphic>` or `<inline-graphic>`
- only plain text (no formatting)

Use `<alt-text>` for **longer** or structured alternative text
- a separate child element within `<fig>`, `<table-wrap>`, or `<media>`.
- allows structure/mark-up (e.g. bold, italics, links)
- use for for complex figures that need detailed descriptions

Use **both**
- when the JATS XML will be transformed into multiple output formats (e.g. HTML, PDF, EPUB)
- screen readers will first read `@alt`
- users needing more details can access `<alt-text>`

#### `<alt-text>`vs `<long-desc>`
Use `<long-desc>` for detailed, structured descriptions. For example, complex figures, charts, and infographics that require in-depth explanations.

- extensive descriptions, patterns, methodology, interpretation
- can have multiple paragraphs, hyperlinks, references
- screen readers do not read it by default but allow users to navigate to it.

In short, use it if an image is highly complex. Combine it with `<alt-text>` so users have a short, immediate summary and can go to the `<long-desc>` for an in-depth explanation.

## Example 2. Tables

### current JATS

```xml
<table-wrap id="tab1">
<table id="table1" width="1*">
<colgroup>
<col width="0.20*"/>
<col width="0.80*"/>
</colgroup>
<tbody>
<tr>
<td><italic>Maget</italic></td>
<td>1) <italic>Volwassen of huwbaar meisje, maagd, jonkvrouw, ongehuwde vrouw</italic>; 2) Ook van <italic>een ongehuwd jonkman, een man</italic> &#x201E;die nie wijf en kende&#x201D;; 3) <italic>Eene ongehuwde vrouw of meisje in dienstbaarheid, dienstmaagd</italic></td>
</tr>
<tr>
<td><italic>Wijf</italic></td>
<td>1) <italic>Vrouw, vrouwspersoon, vrouw in het algemeen</italic>; ook <italic>jonge vrouw, meisje</italic>; vgl. joncwijf; 2) In ongunstigen zin. <italic>Zedelooze vrouw</italic>; <italic>lichtekooi</italic>; 3) <italic>Gehuwde vrouw</italic>; 4) <italic>Van Maria, de Moeder Gods</italic>; 5) <italic>Echtgenoote, vrouw</italic>; 6) <italic>Het wijfje van een dier</italic>; 7) <italic>Dienstmaagd, dienstbode</italic></td>
</tr>
<tr>
<td><italic>Vrouwe</italic></td>
<td>1) <italic>Gebiedster, heerscheres, landsvrouwe</italic>; 2) Van <italic>Maria, de hemelkoningin</italic>, ndl. &#x201E;onze lieve <italic>Vrouw</italic>&#x201D;; 3) <italic>Meesteres</italic>; 4) Van zaken en dingen gezegd heeft vrouwe de bet. van <italic>de hoogste, voornaamste, uitstekendste, beste in eene soort</italic>; 5) Vrouwe wordt de uitdrukking voor <italic>deftige dame, vrouw van hooge geboorte of van aanzienlijken stand</italic>, ook <italic>edelvrouw</italic>; 6) <italic>Vrouw</italic> in het algemeen, hetzelfde als wijf; 7) <italic>Vrouw, echtgenoot, vrouw van, huisvrouw</italic> 8) Als tweede lid van eene samenstelling komt vrouwe voor in woorden, waar het de bet. <italic>opzichteres</italic> heeft.</td>
</tr>
</tbody>
</table>
</table-wrap>
```

There are some issues with this XML:

- the table lacks table headers, i.e. `<thead>` and `<th>` elements
- it is missing a description, i.e. a `<caption>` inside `<table>`, or `<title>` inside `<table-wrap>`
- because this table contains textual information, a language tag (`xml:lang="nl"`) should be added
- it is missing row grouping (making it harder to navigate), i.e. `<thead>` and `<tfoot>` are absent
- there is no structural markup for subcategories. Consider using `<list>` elements instead of having item numbers in the `<td>`.

It may also make sense to explicitly associate `<td>` cells with column meaning. For simple tables, `<th scope="col">` is enough. For complex tables, use `<td headers="id_of_th">`.

### correct XML
```xml
<table-wrap id="tab1" xml:lang="nl">
  <title><italic>Maget, wijf</italic> en <italic>vrouwe</italic> in nominale aanspreekvormen: het corpus</title>
  <table id="table1" width="1*">
    <caption>Het <sc>mnw</sc> geeft de volgende betekenissen voor de zelfstandige naamwoorden <italic>maget, wijf</italic> en <italic>vrouwe</italic></caption>
    <colgroup>
      <col width="0.20*"/>
      <col width="0.80*"/>
    </colgroup>
    <thead>
      <tr>
        <th scope="col">Term</th>
        <th scope="col">Definitions</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><italic>Maget</italic></td>
        <td>
          <list list-type="order">
            <list-item><italic>Volwassen of huwbaar meisje, maagd, jonkvrouw, ongehuwde vrouw</italic></list-item>
            <list-item><italic>Ook van een ongehuwd jonkman, een man „die nie wijf en kende”</italic></list-item>
            <list-item><italic>Eene ongehuwde vrouw of meisje in dienstbaarheid, dienstmaagd</italic></list-item>
          </list>
        </td>
      </tr>
      <tr>
        <td><italic>Wijf</italic></td>
        <td>
          <list list-type="order">
            <list-item><italic>Vrouw, vrouwspersoon, vrouw in het algemeen</italic>; ook <italic>jonge vrouw, meisje</italic></list-item>
            <list-item><italic>Zedelooze vrouw</italic>; <italic>lichtekooi</italic></list-item>
            <list-item><italic>Gehuwde vrouw</italic></list-item>
            <list-item><italic>Van Maria, de Moeder Gods</italic></list-item>
            <list-item><italic>Echtgenoote, vrouw</italic></list-item>
            <list-item><italic>Het wijfje van een dier</italic></list-item>
            <list-item><italic>Dienstmaagd, dienstbode</italic></list-item>
          </list>
        </td>
      </tr>
      <tr>
        <td><italic>Vrouwe</italic></td>
        <td>
          <list list-type="order">
            <list-item><italic>Gebiedster, heerscheres, landsvrouwe</italic></list-item>
            <list-item>Van <italic>Maria, de hemelkoningin</italic>, ndl. &#x201E;onze lieve <italic>Vrouw</italic>&#x201D;</list-item>
            <list-item><italic>Meesteres</italic></list-item>
            <list-item>Van zaken en dingen gezegd heeft vrouwe de bet. van <italic>de hoogste, voornaamste, uitstekendste, beste in eene soort</italic></list-item>
            <list-item>Vrouwe wordt de uitdrukking voor <italic>deftige dame, vrouw van hooge geboorte of van aanzienlijken stand</italic>, ook <italic>edelvrouw</italic></list-item>
            <list-item><italic>Vrouw</italic> in het algemeen, hetzelfde als wijf</list-item>
            <list-item><italic>Vrouw, echtgenoot, vrouw van, huisvrouw</italic></list-item>
            <list-item>Als tweede lid van eene samenstelling komt vrouwe voor in woorden, waar het de bet. <italic>opzichteres</italic> heeft</list-item>
          </list>
        </td>
      </tr>
    </tbody>
    <tfoot>
      <tr>
        <td colspan="2">Bron: <sc>mnw</sc></td>
      </tr>
    </tfoot>
  </table>
</table-wrap>
```

#### Summary of fixes:
- ✅ Added `<thead>` with `<th>` headers for better screen reader support.
- ✅ Added `<title>` in `<table-wrap>` and `<caption>` inside `<table>` for clear descriptions.
- ✅ Added `xml:lang="nl"`
- ✅ Used `<scope>` attributes in `<th>` to clarify column relationships.
- ✅ Grouped header and footer properly (`<thead>`, `<tbody>`, `<tfoot>`).
- ✅ Replaced inline numbered lists with `<list>` elements for semantic clarity.

Note that this table does not need alt text because it is textual. For tables, it is good practice to rely on well-structured content (headers, captions, and a clear arrangement) and use `@alt` and `<alt-text>` for any graphical or complex content that requires additional explanation.

Again: if the JATS is not accessible, the HTML cannot be accessible either. We need to fix the JATS and re-upload the content. THen, we need to check if the HTML is accessible.

## see also
Search Confluence [here](https://confluence.ingenta.com/confluence/dosearchsite.action?cql=siteSearch+~+%22accessibility%22&queryString=accessibility).
