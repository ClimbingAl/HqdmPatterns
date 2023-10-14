# What HQDM is, and isn't

These brief points are to stimulate comparisons with other approaches to data modelling:

* [HQDM](https://github.com/hqdmTop/hqdmFramework/wiki) is a conceptual model with formal foundations to enable data integration for any, and all, enterprise business applications.

* [HQDM](https://github.com/hqdmTop/hqdmFramework/wiki) isn't compatible with established data modelling tools and query languages without careful implementation choices.

* [HQDM](https://github.com/hqdmTop/hqdmFramework/wiki) is a data model that can be used (almost) as it is documented.  This documentation covers doing just this.

* [HQDM](https://github.com/hqdmTop/hqdmFramework/wiki) isn't the easiest model to learn BUT it becomes by far the most practical choice when the structures and patterns are employed to exploit the model's inherent properties (like extensibility, immutability and additivity).

When using HQDM as an integration data model for storage and retrieval some structural characteristics of the data should be considered.  This is easy to do with HQDM as it has a single root Entity-Type *thing*, from which all other entity-types inherit.  The next page introduces *thing* as the [Top Level Type](./top_level_type.md).

