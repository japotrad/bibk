# bibk
Xml file format definition for a basic variant of DocBook dedicated to bilingual text documents

## Dual language management
Let’s say we have a document in a source language _so_, translated into a target language _ta_. The bilingual book audience is mainly composed of the target language users. So, the bibk root element should be in _ta_ language, and the source text is added via the _source_ tag. For example:
```xml
<book xml:lang="ta">
 <info>
  <title>Translated title<source xml:lang="so" role="source">Original title</source></title>
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
The document content is an interleave of rich text blocks, figures and separators.

### Rich text block
The following inline elements are supported:
- _citetitle_ for work titles
- _date_ for dates
- _emphasis_ for italic and bold
- _footnote_ for notes
- _foreignphrase_ for words in other languages
- _ruby_ and _rt_ for Japanese furigana

### Figures
- _mediaobject_ for images
- Tables (TBD)
Note: For each figure, up to 3 variants can be prepared: source language only, target language only, bilingual.

### Separators
- _bridgehead_

## Comparison with DocBook 5.2 format
Bibk format restricts DocBook format in many many ways, and extends it for Japanese furigana (_ruby_ & _rt_ tags) and for the source text (_source_ tag).
