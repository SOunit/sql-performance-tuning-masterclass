# client

- user processes
  - send query to db server
  - get some data

# server

- server processes
  - push query to PGA

## PGA / Program Global Area / Private Global Area

- memory cache
- all user has private PGA

## SGA / System Global Area / Shared Global Area

- Shared SQL Area

  - memory cache
  - to handle same queries from multiple users
  - keep `Execution Plan` to reuse

- Database buffer cache
- Redo log buffer
- Shared pool
  - most important memory
  - library cache
  - result cache
    - keep query result
      - 5s for 1st time
      - immediate for 2nd time
    - will be flush / deleted when data changes
  - data dictionary cache
    - save result to cache
      - check if table exist
      - what is the columns for \*
