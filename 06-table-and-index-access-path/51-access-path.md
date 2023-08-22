- access path

  - how to fetch row from row-sources
  - important to read execution plan well
  - need to show better access path to sql optimizer

- main access path

  - table access path
    - table access full
      - read whole table and return required rows
    - table access by rowId
      - read by jump to id to id
    - sample table scan
      - read certain portion of table, not accurate, but fast
      - have to activate this manually
  - index access path
    - Index Unique Scan
      - return 1 row id only
    - Index Range scan
      - if row is more than 1
    - index full scan
      - group by or order by need all rows
    - index fast full scan
      - in case index already exist in current index in hand
    - index skip scan
      - ignore empty values
    - index join scan
      - join 2 or more indexes in memory for fast search
    - index organized table
      - do not need all where clause variables
    - bitmap access path
      - convert b-tree to bitmap access for performance

- if fetch most of the rows

  - use table access

- join and access path is main reason for bad sql query
