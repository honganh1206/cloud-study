---
id: Windowing Functions
aliases:
  - Windowing Functions
tags: []
---

# Windowing Functions

Group events into time-based segments for analysis during real-time data streaming

Help processing continuous, unbounded data by _applying aggregations_ like count/sum/max/etc.

Divide the data into manageable chunks

Used by transformation in Eventstream Group

Types:

[[Tumbling Window]]

[[Hopping Window]]

[[Sliding Window]]

[[Session Window]]

[[Snapshot]]

![[Pasted image 20250412222537.png]]

Other properties:

**Window duration** is the length of each window interval

**Window offset** is an optional parameter that shifts the start and end of each window interval by a specified amount of time. An example is an offset of 2 minutes meaning each window starts and ends 2 minutes later than usual

**Grouping key** is one or more columns in the event data to group by

**Aggregate function** is the functions we can apply to each group of events in each window



