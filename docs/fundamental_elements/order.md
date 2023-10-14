# Order

This is perhaps the most easily overlooked, and hardest to address, fundamental relation.  The concept of ordering lists, events, sequences, etc is a familiar activity in computing, engineering, information management, etc.  However, addressing aspects of order is hard if we want to maintain internal consistency (within the model).  Even the apparently simple notion of a relationship in data, as illustrated in the various node-edge diagrams, has an order to it (start - rel - end, sometimes referred to as the domains and ranges of each named relationship):

--8<-- "relNodeEdgeGraph.mermaid"

There are a number of applications of order in data models but for our integration data model we have 4-dimensionalist commitments.  These include dealing with events (that are temporal boundaries of states, one at the start, `beginning`, and end, `ending`) and various ways of ordering those events (perhaps with a metric that represents time such as a date-time record):

--8<-- "orderEventsNodeEdgeGraph.mermaid"

Other topics to expand upon include: 

- Additional aspects of order; sequences, lists, ordered pairs and tuples.
- Advanced topic for the extension of HQDM to address `multidimensional_objects` (although this name for them may be sub-optimal), using 15926-2 as an example.
