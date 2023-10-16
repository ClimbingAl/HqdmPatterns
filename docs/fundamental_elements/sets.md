# Set membership

Another key fundamental relation is that of set membership.  Although optional, the separation of _types_ and the sets that elements of those _types_ can be members of is a key feature of HQDM.  This allows a single item to be assigned membership of as many sets as is required.  It also provides a means of creating subsets (specialisations) of the elements that are all of the same Entity _type_ and even sets that have elements from an arbitrary range of types (e.g. the set of things in my garage last weekend).

??? note
    It should now be apparent that sets are created as data that is within the model framework.  This can allow the addition of sets as data without having to re-build the software, a common issue when adding classes to data models that require the software that implements the model to be rebuilt each time the model is changed.
    There will be times when the software that implements HQDM needs to be re-built but this is generally due to decisions around the way that model patterns are implemented, stored or adopted; in the limit, an infrequent and less-limiting occurrence.

The first set membership example shows the state of the Lunar Lander LM-5 when it was on the moon as being `member_of` a specialisation of `class_of_state_of_physical_object` that has the name "ClassOfStateOfPhysicalObject
__State_Of_Lunar_Lander" (a set that is intended only for states of lunar landers).  

!!! warning
    Although this is a human-created set, "intended only for states of lunar landers" we should be careful how it is handled within the logic of the model.  The model is extensional; the sets are defined by their membership.  If a set has no members, it is an empty set and has no inherent meaning.  If it has members that are incorrectly assigned to it there is no way for a computer to tell if it is incorrectly assigned (unless a detectable model violation has occurred, something that should have been caught before the record was created).  Ensuring that sets have the correct members is a matter of data quality and ultimately will be a business decision.  Of course, HQDM has features that lend its use to continuous improvement.  This will be discussed in **Section TBC. Set goal to model to one level of detail beyond what's currently required.**.

We could have created other sets for this state of Lunar Lander LM-5 to be `member_of` (e.g. the set of states of Lunar Landers that have successfully landed on the moon) but it is prudent to only create sets that are needed.  We don't yet have a case for creating sets beyond the declared one that is committed to be for states of lunar landers.

--8<-- "member_ofNodeEdgeGraph.mermaid"

A specialisation of `member_of` is `member_of_kind`.  A set that is used to assign elements to it with this relation implies that all of the members are of the same kind for the whole of their existence (as wholes).  Such elements will be of the _type_ `individual` or any of its sub-types.  Our example for the Apollo-11 Lunar Landing is that the Lunar Lander LM-5 existed for a period of time longer than its existence on the surface of the moon.  It's whole-life state is therefore a `member_of_kind` of a specialisation of `kind_of_physical_object` that has the human-readable name "_KindOfPhysicalObject__Lunar_Lander_" (a set intended only for whole-life lunar landers).

--8<-- "member_of_kindNodeEdgeGraph.mermaid"
