# bibk
Xml file format definition for a basic variant of DocBook dedicated to bilingual text documents

## Dual language management
Let’s say we have a document in a source language _so_, translated into a target language _ta_. The bilingual book audience is mainly composed of the target language users. So, the bibk root element should be in _ta_ language, and the source text is added via the _foreignphrase_ tag. For example:
```xml
<book xml:lang="ta">
 <info>
  <title>Translated title<foreignphrase xml:lang="so" role="source">Original title</foreignphrase></title>
 </info>
</book>
```

## Description of the format
### Document metadata in _book_/_info_
- Title, subtitle
- Author, translator...
- Publisher, publication date, ISBN...

### Document content structure
Three structures are supported :
- Single article
- List of chapters
- List of parts containing chapters

### Backmatter
- Appendix
- Index

## Expressive capability of document content
### Figures
 - Images
 - Tables

Note: For each figure, up to 3 variants can be prepared: source language only, target language only, bilingual.
### Rich text block
The following inline elements are supported:
- _citetitle_ for work titles
- _date_ for dates
- _emphasis_for italic
_ _foreignphrase_ for words in other languages
- _ruby_ and _rt_ for Japanese furigana
- _footnote_ for notes

## Comparison with DocBook 5.2 format
Bibk format restricts DocBook format in many many ways. The only formal extension it adds is Japanese furigana (_ruby_ & _rt_ tags). The main semantic tweak is related to _foreignphrase_ element with _role="source"_ attribute, which exposes the original text in the source language.
A valid Bibk document with no furigana should be valid regarding the DocBook relaxng. (Only limited tested have been performed.)
