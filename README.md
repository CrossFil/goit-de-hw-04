# Exploring Spark UI

This assignment focuses on understanding how Spark executes transformations and actions by analyzing **Spark UI** job execution.

## Part 1 — Basic Job Flow

- Load a CSV dataset and apply several transformations.
- Execute `.collect()` at the end to trigger computation.
- **Expected: 5 Jobs** in Spark UI.

## Part 2 — Intermediate Action

- Add an additional `.collect()` before the final transformation.
- This triggers an extra computation stage.
- **Expected: 8 Jobs** in Spark UI.
- Why? Each `.collect()` is an action that forces Spark to compute from the source.

## Part 3 — Using Cache

- Apply `.cache()` before the first `.collect()`.
- Prevents recomputation of the same transformations.
- **Expected: 7 Jobs** in Spark UI.
- Cached data is reused for the second action, reducing job count.
