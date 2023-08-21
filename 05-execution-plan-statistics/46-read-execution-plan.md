- mainly tuning on I/O cost
- optimization type

  - cost-based optimization
  - rule-based optimization
    - old, not recommended now

- all-row, row-n, first-row

  - limit rows to show users response faster

- where to look

  - cost
  - access methods
    - see if full table scan?
    - can change to another access methods
  - cardinality
  - join methods & join types
  - partition pruning
    - pruning means remove unnecessary partition scan
    - just scan minimum partition and better performance

- fix query
  - `in` operation
    - make high cost
    - analyzer uses `or` condition, `or` is slow
  - change `in` to `between`
    ```
    id in (1,2,3,4,5)
    ```
    ```
    id between 1 and 5
    ```
