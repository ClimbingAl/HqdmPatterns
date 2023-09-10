# Parts

Our first fundamental sort of relation is that of parthood (one thing being part of another).  Only material things (real, actual stuff) can be part of something else that is also materially real.  The top layer, filling, bottom layer and any decorations are all part of an actual cake that is composed of them.  The state of you as you are reading this page is part of the state of you that existed before (and likely exists after) you read this page.

The root predicate for all parthood relations is `part_of`, where one material thing is part of another whole.  All other part-based relations are specialisations of `part_of`.

??? note
    The term *specialisation* is used here to avoid using other terms like _sub-type_, _sub-set_ or _sub-class_ as they have their own roles in HQDM.

A commonly used parthood relation is `temporal_part_of`, where a state of something physical is a whole-part (i.e. all of it), of that physical thing, for a period of time.  The Apollo-11 Lunar Lander Module called "Eagle" rested on the surface of the moon for just over 21hrs.  During that time the state of that Lunar Lander Module was a part of its existence for a well-documented period of time.  This is shown in the node-edge graphs below.  Firstly, the `temporal_part_of` relation is shown between the two data objects:

--8<-- "temporalPartOfNodeEdgeGraph.mermaid"

The events bounding the state of the LM-5 lander are shown in the next diagram.  The events are points in time (`point_in_time`) that have ISO-8601 DateTime stamps to record the instant in time.  More detail on the handling of `point_in_time` records can be seen in the source TURTLE file.  The use of the `data_EntityName` relation is a compromise discussed **Here TBC Sign And Pattern**.

--8<-- "temporalPartOfIncEventsNodeEdgeGraph.mermaid"

Another common parthood relation is `part_of_possible_world`.  All material things exist in at least one _possible world_.  The node-edge graph belows shows the same Lunar Lander states from the example above existing in the same `possible_world`.

--8<-- "temporalPartOfAllRelsNodeEdgeGraph.mermaid"