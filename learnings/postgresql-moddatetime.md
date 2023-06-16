  # Automatically handle `updated_at` column

> **[moddatetime()](https://www.postgresql.org/docs/current/static/contrib-spi.html)** is a trigger that stores the current time into a timestamp field. This can be useful for tracking the last modification time of a particular row within a table.
>
> To use, create a BEFORE UPDATE trigger using this function. Specify a single trigger argument: the name of the column to be modified. The column must be of type timestamp or timestamp with time zone.

  ```sql
create extension if not exists moddatetime schema extensions;

-- assuming the table name is "todos", and a timestamp column "updated_at"
-- this trigger will set the "updated_at" column to the current timestamp for every update
create trigger handle_updated_at before update on todos
  for each row execute procedure moddatetime (updated_at);
```
