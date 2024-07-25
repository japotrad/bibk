# bibk
Xml file format definition for a basic variant of DocBook dedicated to bilingual text documents

## Dual language management
Let’s say we have a document in a source language _so_, translated into a target language _ta_. The bilingual book audience is mainly composed of the target language users. So, the bibk root element should be in _ta_ language, and the source text is added via the _foreignphrase_ tag. For example:
```xml
<book xml:lang="ta">
  <info>
	   <title>Translated title<foreignphrase xml:lang="so" role="source">Original title</foreignphrase></title>
  </info>
<book>
```

## Description of the format
### Document metadata in book/info
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