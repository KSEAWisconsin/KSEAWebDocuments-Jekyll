# YAML

**YAML** ( a [recursive acronym](https://en.wikipedia.org/wiki/Recursive_acronym) for "YAML Ain't Markup Language") is a human-readable data-serialization language.

- *Whitespace indentation* is allowed but not tab characters.
- Comments begin with the number sign (`#`)
  - Comments must be separated from other tokens by whitespace characters
  - If # appear inside of a string, just a number sign (#)
- List members are denoted by a leading hyphen (`-`) with one member per line
  - Also can be specified by square brackets (`[ ]`) with separated by commas
- Can use *key: value* using colon space with on entry per line
  - Curly braces (`{ }`) can produce assiciative array
  - Entries are separated by comman (no spaces are necessary)
- Strings are specified by enclosed double-quotes (`"`) or single-quotes (`'`)
- Block scalars are delimited with indentation with optional modifiers to preserve (`|`) or fold (`>`) newlines
- Multiple documents within a single stream are separated by **three hyphens (`---`)**
  - Three periods (`...`) optionally end a document within a stream
- **Repeated nodes** are initially denoted by an ampersand (`&`) and thereafter referenced with an asterisk (`*`)
- Nodes may be labeled with a type or tag using the exclamation point (`!!`) followed by a string, which can be expanded into a URI
- With a percent sign (`%`) followed by 

