## Reference
This section lists all possible objects and fields.

### `corpus`

|                  |                                                                                           |
| ---------------- | ----------------------------------------------------------------------------------------- |
| **Type:**        | object                                                                                    |
| **Description:** | The root object holds metadata and a collection of documents associated with this corpus. |
| **Parent:**      | N/A                                                                                       |
| **Fields:**      | [metadata](#metadata) \| [documents](#documents)                                          |
| **Example:**     | <pre lang="json">{<br>  "metadata": { ... },<br>  "documents": [ ... ]<br>}</pre>         |


### `metadata`

|                  |                                                                                                                      |
| ---------------- | -------------------------------------------------------------------------------------------------------------------- |
| **Type:**        | object                                                                                                               |
| **Description:** | The metadata contains information about the corpus.                                                                  |
| **Parent:**      | [corpus](#corpus)                                                                                                    |
| **Fields:**      | [authors](#authors) \| [description](#description)                                                                   |
| **Example:**     | <pre lang="json">"metadata": {<br>  "authors": [ ... ],<br>  "description": { ... },<br>  // other fields<br>}</pre> |

#### `authors`

|                  |                                                                                                  |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| **Type:**        | array                                                                                            |
| **Description:** | Lists the individuals responsible for creating and/or contributing to the content of the corpus. |
| **Parent:**      | [metadata](#metadata)                                                                            |
| **Fields:**      | [author](#authors)                                                                               |
| **Example:**     | <pre lang="json">"authors": [<br>  { ... },<br>  { ... }<br>]</pre>                              |

### `author`

|                  |                                                                                                                         |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------- |
| **Type:**        | object                                                                                                                  |
| **Description:** | An individual responsible for creating and/or contributing to the content of the corpus.                                |
| **Parent:**      | [authors](#authors)                                                                                                     |
| **Fields:**      | [first name](#first-name) \| [last name](#last-name) \| [email](#email)                                                 |
| **Example:**     | <pre lang="json">{<br>  "first-name": "John",<br>  "last-name": "Brown",<br>  "email": "jbrown@mail.com"<br>}<br></pre> |

### `first-name`

|                  |                                             |
| ---------------- | ------------------------------------------- |
| **Type:**        | string                                      |
| **Description:** | First name of the author                    |
| **Parent:**      | [author](#author)                           |
| **Fields:**      | N/A                                         |
| **Example:**     | <pre lang="json">"first-name": "John"</pre> |

### `last-name`

|                  |                                             |
| ---------------- | ------------------------------------------- |
| **Type:**        | string                                      |
| **Description:** | First name of the author                    |
| **Parent:**      | [author](#author)                           |
| **Fields:**      | N/A                                         |
| **Example:**     | <pre lang="json">"last-name": "Brown"</pre> |

### `email`

|                  |                                                   |
| ---------------- | ------------------------------------------------- |
| **Type:**        | string                                            |
| **Description:** | First name of the author.                         |
| **Parent:**      | [author](#author)                                 |
| **Fields:**      | N/A                                               |
| **Example:**     | <pre lang="json">"email": "jbrown@mail.com"</pre> |

### `description`

|                  |                                                        |
| ---------------- | ------------------------------------------------------ |
| **Type:**        | string                                                 |
| **Description:** | Description of the object                              |
| **Parent:**      | [document](#document) \| [metadata](#metadata)         |
| **Fields:**      | N/A                                                    |
| **Example:**     | <pre lang="json">"description": "My description"</pre> |

### `created`

|                  |                                                 |
| ---------------- | ----------------------------------------------- |
| **Type:**        | string                                          |
| **Description:** | Date on which the corpus was initially created. |
| **Parent:**      | [metadata](#metadata)                           |
| **Fields:**      | N/A                                             |
| **Example:**     | <pre lang="json">"created": "2024-01-01"</pre>  |

#### `documents`

|                  |                                                                       |
| ---------------- | --------------------------------------------------------------------- |
| **Type:**        | array                                                                 |
| **Description:** | List of document objects associated with the corpus                   |
| **Parent:**      | [corpus](#corpus)                                                     |
| **Fields:**      | [document](#document)                                                 |
| **Example:**     | <pre lang="json">"documents": [<br>  { ... },<br>  { ... }<br>]</pre> |

#### `document`

|                  |                                                                                                   |
| ---------------- | ------------------------------------------------------------------------------------------------- |
| **Type:**        | object                                                                                            |
| **Description:** | A document object associated with the corpus                                                      |
| **Parent:**      | [documents](#documents)                                                                           |
| **Fields:**      | [description](#description) \| [id](#id) \| [sentences](#sentences)                               |
| **Example:**     | <pre lang="json">"document": {<br>  "id": 1,<br>  "sentences": [<br>    { ... }<br>  ]<br>}</pre> |

#### `sentences`

|                  |                                                                       |
| ---------------- | --------------------------------------------------------------------- |
| **Type:**        | array                                                                 |
| **Description:** | List of sentence objects associated with the document                 |
| **Parent:**      | [document](#document)                                                 |
| **Fields:**      | [sentence](#sentence)                                                 |
| **Example:**     | <pre lang="json">"sentences": [<br>  { ... },<br>  { ... }<br>]</pre> |

#### `sentence`

|                  |                                                                                                |
| ---------------- | ---------------------------------------------------------------------------------------------- |
| **Type:**        | object                                                                                         |
| **Description:** | List of sentence objects associated with the document                                          |
| **Parent:**      | [documents](#documents)                                                                        |
| **Fields:**      | [id](#id) \| [language](#language) \| [tokens](#tokens)                                        |
| **Example:**     | <pre lang="json">"sentence": {<br>  "id": 1,<br>  "tokens": [<br>    { ... }<br>  ]<br>]</pre> |

#### `tokens`

|                  |                                                                    |
| ---------------- | ------------------------------------------------------------------ |
| **Type:**        | array                                                              |
| **Description:** | List of token objects associated with the sentence                 |
| **Parent:**      | [document](#sentence)                                              |
| **Fields:**      | [token](#token)                                                    |
| **Example:**     | <pre lang="json">"tokens": [<br>  { ... },<br>  { ... }<br>]</pre> |

#### `token`

|                  |                                                                                                                                                                            |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Type:**        | object                                                                                                                                                                     |
| **Description:** | A token object  associated with the corpus                                                                                                                                 |
| **Parent:**      | [sentence](#sentence)                                                                                                                                                      |
| **Fields:**      | [id](#id) \| [form](#form) \| [lemma](#lemma) \| [upos](#upos) \| [xpos](#xpos) \| [feats](#feats) \| [head](#head) \| [deprel](#deprel) \| [deps](#deps) \| [misc](#misc) |
| **Example:**     | <pre lang="json">"sentence": {<br>  "id": 1,<br>  "tokens": [<br>    { ... }<br>  ]<br>]</pre>                                                                             |

#### `form`

|                  |                                             |
| ---------------- | ------------------------------------------- |
| **Type:**        | string                                      |
| **Description:** | Word form or punctuation symbol.            |
| **Parent:**      | [token](#token)                             |
| **Fields:**      | N/A                                         |
| **Example:**     | <pre lang="json">"form": "authorized"</pre> |

#### `lemma`

|                  |                                             |
| ---------------- | ------------------------------------------- |
| **Type:**        | string                                      |
| **Description:** | Lemma or stem of word form.                 |
| **Parent:**      | [token](#token)                             |
| **Fields:**      | N/A                                         |
| **Example:**     | <pre lang="json">"lemma": "authorize"</pre> |

#### `upos`

|                  |                                       |
| ---------------- | ------------------------------------- |
| **Type:**        | string                                |
| **Description:** | Universal part-of-speech tag.         |
| **Parent:**      | [token](#token)                       |
| **Fields:**      | N/A                                   |
| **Example:**     | <pre lang="json">"upos": "VERB"</pre> |

#### `xpos`

|                  |                                                                                       |
| ---------------- | ------------------------------------------------------------------------------------- |
| **Type:**        | string                                                                                |
| **Description:** | Optional language-specific (or treebank-specific) part-of-speech / morphological tag. |
| **Parent:**      | [token](#token)                                                                       |
| **Fields:**      | N/A                                                                                   |
| **Example:**     | <pre lang="json">"xpos": "V"</pre>                                                    |

#### `feats`

|                  |                                                                                                                    |
| ---------------- | ------------------------------------------------------------------------------------------------------------------ |
| **Type:**        | string                                                                                                             |
| **Description:** | List of morphological features from the universal feature inventory or from a defined language-specific extension. |
| **Parent:**      | [token](#token)                                                                                                    |
| **Fields:**      | N/A                                                                                                                |
| **Example:**     | <pre lang="json">"feats": "Tense=Past\|VerbForm=Part"</pre>                                                        |

#### `head`

|                  |                                                                      |
| ---------------- | -------------------------------------------------------------------- |
| **Type:**        | string                                                               |
| **Description:** | Head of the current word, which is either a value of ID or zero (0). |
| **Parent:**      | [token](#token)                                                      |
| **Fields:**      | N/A                                                                  |
| **Example:**     | <pre lang="json">"head": "1"</pre>                                   |

#### `deprel`

|                  |                                                                                                             |
| ---------------- | ----------------------------------------------------------------------------------------------------------- |
| **Type:**        | string                                                                                                      |
| **Description:** | Universal dependency relation to the HEAD (root if HEAD = 0) or a defined language-specific subtype of one. |
| **Parent:**      | [token](#token)                                                                                             |
| **Fields:**      | N/A                                                                                                         |
| **Example:**     | <pre lang="json">"deprel": "advcl"</pre>                                                                    |

#### `deps`

|                  |                                                                       |
| ---------------- | --------------------------------------------------------------------- |
| **Type:**        | string                                                                |
| **Description:** | Enhanced dependency graph in the form of a list of head-deprel pairs. |
| **Parent:**      | [token](#token)                                                       |
| **Fields:**      | N/A                                                                   |
| **Example:**     | <pre lang="json">TODO</pre>                                           |

#### `misc`

|                  |                      |
| ---------------- | -------------------- |
| **Type:**        | string               |
| **Description:** | Any other annotation |
| **Parent:**      | [token](#token)      |
| **Fields:**      | N/A                  |
| **Example:**     | N/A                  |

#### `language`

|                  |                                                                    |
| ---------------- | ------------------------------------------------------------------ |
| **Type:**        | string                                                             |
| **Description:** | A language identifier                                              |
| **Parent:**      | [document](#documents) \| [sentence](#sentence) \| [token](#token) |
| **Fields:**      | N/A                                                                |
| **Example:**     | <pre lang="json">"language": "en"</pre>                            |

#### `id`

|                  |                                                                   |
| ---------------- | ----------------------------------------------------------------- |
| **Type:**        | int                                                               |
| **Description:** | Unique identifier                                                 |
| **Parent:**      | [document](#document) \| [sentence](#sentence) \| [token](#token) |
| **Fields:**      | N/A                                                               |
| **Example:**     | <pre lang="json">"id": 1</pre>                                    |