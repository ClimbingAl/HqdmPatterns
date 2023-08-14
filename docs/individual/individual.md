# 'Whole-life' Individual

## **individual** Entity Type

One of the first HQDM patterns that is key to many of the more involved patterns is that of 'whole-life' [`individual`](https://github.com/hqdmTop/hqdmFramework/wiki/individual).  



### Supertype Hierarchy
--8<-- "individualAndPhyscialObjectSupertypes.mermaid"

### Relations
--8<-- "individualAndPhyscialObjectRels.mermaid"

## Implementation


Other properties may be chosen, or added, for additional data management purposes (e.g. logical deletion or data record copying).  They are described in the HQDM References below and are provided in the [`PatternsUtils.java`](https://github.com/ClimbingAl/code-for-hqdm-patterns/blob/cb73d64e61fda53b48af49f2793d6761ba79cd2a/thing/thing/src/main/java/patterns/hqdm/PatternsUtils.java#L31).

## Example
Instance of ```thing``` generated by the [`ThingExample`](https://github.com/ClimbingAl/code-for-hqdm-patterns/blob/prefixes/thing/thing/src/main/java/patterns/hqdm/ThingApp.java).

--8<-- "thingObject.mermaid"

``` title="Individual object in TURTLE" hl_lines="5-8"
--8<-- "individual.ttl"
```
While it is unusual to create instances of the `thing` entity-type, this is the data object structure that will be used for all its sub-types, with the only addition being relationships (as RDF predicates) that are committed in the HQDM model (and, therefore, its patterns).

## References

HQDM book references: 6.3.7, 7.2.1 & 7.3

MagmaCore (Java) reference: [HQDM Object](https://github.com/gchq/MagmaCore/blob/879e8f119f8defef457ba0caa366ee4aa3335bab/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/pojo/HqdmObject.java#L28C1-L28C1), [Thing](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/model/Thing.java)

Other implementation issues:

