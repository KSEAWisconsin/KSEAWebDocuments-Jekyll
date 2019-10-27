# YAML
[Official site](https://yaml.org/)


**YAML** ( a [recursive acronym](https://en.wikipedia.org/wiki/Recursive_acronym) for "YAML Ain't Markup Language") is a human-readable data-serialization language.

- *Whitespace indentation* is allowed but not tab characters.
- Comments begin with the number sign (`#`)
  - Comments must be separated from other tokens by whitespace characters
  - If # appear inside of a string, just a number sign (#)
- List members are denoted by a leading hyphen (`-`) with one member per line
  - Also can be specified by square brackets (`[ ]`) with separated by commas
- Multiple documents within a single stream are separated by **three hyphens (`---`)**
```
 --- # Favorite movies
 - Joker
 - Avengers Endgame
 - [The King, Terminator]
```

- Can use *key: value* using colon space with on entry per line
  - Curly braces (`{ }`) can produce assiciative array
  - Entries are separated by comman (no spaces are necessary)
```
 --- # Indented Block
   name: Yongsang Park
   age: 20
 --- # Inline Block
 {name: Yongsang Park, age: 20}
```

- Strings are specified by enclosed double-quotes (`"`) or single-quotes (`'`)
- Block scalars are delimited with indentation with optional modifiers to preserve (`|`) or fold (`>`) newlines
  - Can use multiple line
```
data: |
   There once was a tall man from Ealing
   Who got on a bus to Darjeeling
       It said on the door
       "Please don't sit on the floor"
   So he carefully sat on the ceiling
```

  - Three periods (`...`) optionally end a document within a stream
- **Repeated nodes** are initially denoted by an ampersand (`&`) and thereafter referenced with an asterisk (`*`)
- Nodes may be labeled with a type or tag using the exclamation point (`!!`) followed by a string, which can be expanded into a URI
- With a percent sign (`%`) followed by a name and space delimited parameters
  - %YAML: identifying the **version** of YAML in a given document
  - %TAG: shortcut for URI prefixes

### Some examples to examine
```
--- # The Smiths
- {name: John Smith, age: 33}
- name: Mary Smith
  age: 27
- [name, age]: [Rae Smith, 4]   # sequences as keys are supported
--- # People, by gender
men: [John Smith, Bill Jones]
women:
  - Mary Smith
  - Susan Williams
```

```
# sequencer protocols for Laser eye surgery
---
- step:  &id001                  # defines anchor label &id001
    instrument:      Lasik 2000
    pulseEnergy:     5.4
    pulseDuration:   12
    repetition:      1000
    spotSize:        1mm

- step: &id002
    instrument:      Lasik 2000
    pulseEnergy:     5.0
    pulseDuration:   10
    repetition:      500
    spotSize:        2mm
- step: *id001                   # refers to the first step (with anchor &id001)
- step: *id002                   # refers to the second step
- step:
    <<: *id001
    spotSize: 2mm                # redefines just this key; refers to &id001 for the rest
- step: *id002
```

```
---
receipt:     Oz-Ware Purchase Invoice
date:        2012-08-06
customer:
    first_name:   Dorothy
    family_name:  Gale

items:
    - part_no:   A4786
      descrip:   Water Bucket (Filled)
      price:     1.47
      quantity:  4

    - part_no:   E1628
      descrip:   High Heeled "Ruby" Slippers
      size:      8
      price:     133.7
      quantity:  1

bill-to:  &id001
    street: |
            123 Tornado Alley
            Suite 16
    city:   East Centerville
    state:  KS

ship-to:  *id001

specialDelivery:  >
    Follow the Yellow Brick
    Road to the Emerald City.
    Pay no attention to the
    man behind the curtain.
...
```
