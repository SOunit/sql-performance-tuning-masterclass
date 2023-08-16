# SGA / Shared Global Area

- Library cache
  - organizer for Shared SQL Area
    - delete least used stored SQL if memory is full
  - Shared SQL Area
    - store shared SQL to reuse
- Buffer cache
  - to avoid access hardware many and many times
  - get data and return to server process instead of access hardware
  - fetch data from hardware and save the result to reuse
- Redo log buffer
  - keep initial data
- Java pool
  - keep instance for db
- Streams pool
  - handle stream
