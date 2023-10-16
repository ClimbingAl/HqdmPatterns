# Relations

Relations in a Top Level Data Model, and data based on it, are fundamental and have some formal characteristics.  They represent what one item (thing/object/type, etc) has to do with another AND about which there is "nothing more to say".  If a relationship is expressed between two items then it is logically present (`TRUE`).  However, these binary relations are more restricted than the relations present in mathematical set theory (e.g. they can't be symmetric).  They always have an order and therefore represent a set of ordered pairs, or an ordered pair that is an element of such a set.

The three foundational relationship groups in HQDM are:

- [parts](./parts.md)
- [sets](./sets.md)
- [order](./order.md)

Topics on relations that may be added, if there is interest: 

- Relations and instances of them.  How to implement and query for them generally.
- Supertype-subtype relations are really important (especially considering the multiple-inheritance characteristics of HQDM) but are easy to overlook.  Handling them in code may be worth documenting further.
- Specialisation of relations.  The foundational relations (*parts*, *sets* and *order*) in HQDM have many specialisations.  This is not formalised in most implementations but there is a specialisation hierarchy for most of the relations in HQDM.  This, combined with the type-hierarchy, could provide a path towards a Domain Specific Language for interacting with the data (and the patterns documented on this site).
- [EXPRESS](https://en.wikipedia.org/wiki/EXPRESS_(data_modeling_language)) as a data modelling language has the ability to redeclare relations.  This is intended to assert that when a subtype inherits a relation from a supertype that relation is a required feature of the subtype (rather than just inheriting the wider-scope of that relation from its supertype).  Handling this in the implementation of HQDM may benefit from further work.
