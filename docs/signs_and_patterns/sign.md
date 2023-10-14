## **sign** Entity Type

??? question "What information requirement does this meet?"
    It is common to require information about how material things are identified, or named, using [signs](./what_are_signs.md).  Examples include:

    - The identifier that is used to unambiguously refer to something (e.g. VIN number, passport number, MAC address).  This can allow formal documents, asset records and licensing conditions to refer to the thing that is allocated that identifier (either permanently, at least for much of its existence, or for part of it)

    - Keeping records of names, nicknames, spelling differences of people, other physical items and activities (such as projects).

    - ...

    The `sign` model pattern can be crucial in keeping track of anything that there is an information requirement about.  It is important to note here that the unique identifier used as a key for data objects based on HQDM (such as in Magma Core) are nothing to do with the *signs* that are used to name & refer to the physical items that these data objects represent.  

This `sign` pattern is one of the mode advanced HQDM data model patterns but it is based on the [`association`](../association/association.md) pattern.  The [`sign`](https://github.com/hqdmTop/hqdmFramework/wiki/sign) Entity Type is a whole-life individual for the period of the existence of an actual `sign`. [`representation_by_sign`](https://github.com/hqdmTop/hqdmFramework/wiki/representation_by_sign) is an `association` between a `state_of_sign` and a community that recognises that sign in the context required ([recognizing_language_community](https://github.com/hqdmTop/hqdmFramework/wiki/recognizing_language_community)).  Each of those states are `participant_in` `representation_by_sign` and `represent` some `thing`.

??? info "Types-Supertype Hierarchy"
    The Entity Type [`sign`](https://github.com/hqdmTop/hqdmFramework/wiki/sign) is a subtype of [`individual`](https://github.com/hqdmTop/hqdmFramework/wiki/individual) and [`state_of_sign`](https://github.com/hqdmTop/hqdmFramework/wiki/state_of_sign).  A [`representation_by_sign`](https://github.com/hqdmTop/hqdmFramework/wiki/representation_by_sign) can be a `member_of` one or more [`class_of_representation`](https://github.com/hqdmTop/hqdmFramework/wiki/class_of_representation).  A `representation_by_sign` `consists_of` one or more [`sign`](https://github.com/hqdmTop/hqdmFramework/wiki/sign) states, each of which will be a `member_of_kind` of one or more [`role`](https://github.com/hqdmTop/hqdmFramework/wiki/role)(1), and `consists_of_` one or more [`recognizing_language_community`](https://github.com/hqdmTop/hqdmFramework/wiki/recognizing_language_community).  The `sign` and `recognizing_language_community` states that it `consists_of` all share the same period of time (the same temporal extent) that the `representation_by_sign` association exists for but the `thing` that it `represents` need not have any temporal overlap with the `representation_by_sign`.
    { .annotate }

    1.  The inclusion of `role` in this description is a logical (& natural) consequence of the type inheritance in HQDM.  However, despite being a entailment of the conceptual model, it isn't necessary to use it in implementation (every `sign` can be considered to be of the same *kind*).  It won't feature in our worked examples.

    --8<-- "signTypesSupertypes.mermaid"

## Spacetime Diagram
The following diagram illustrates the association of two states, each state being a `temporal_part_of` an `individual` X and Y respectively.  The constituent states in this `association` all share the same temporal bounds.  This examples will be implemented below to illustrate the general entity-relationship and data patterns resulting from it.

![An association between a state of X and a state of Y](../extras/source-images/signInitial.svg)

## References

HQDM book references: 13.9, 17.45

Entity Types: [`sign`](https://github.com/hqdmTop/hqdmFramework/wiki/sign), [`representation_by_sign`](https://github.com/hqdmTop/hqdmFramework/wiki/representation_by_sign), [`recognizing_language_community`](https://github.com/hqdmTop/hqdmFramework/wiki/recognizing_language_community)

MagmaCore (Java) reference: [`sign`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/model/Sign.java), [`representation_by_sign`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/model/RepresentatioBySign.java)

Source code for this example is available [here](https://github.com/ClimbingAl/code-for-hqdm-patterns/blob/main/patterns/src/main/java/patterns/hqdm/sign/SignExample.java)