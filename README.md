# Lean4 SQL Utils

This repository is a collection of utilities that were split off from lean4 sql initiatives such as ([LeanMySQL](https://github.com/arthurpaulino/LeanMySQL), [lean-postgres](https://github.com/FWuermse/lean-postgres)) as they could be shared across different dialects.

## Installation

### Lake

Add the following dependency to your `lakefile.lean`:

```
package your-package where
  dependencies := #[{
    name := `«sql-utils»
    src := Source.git "https://github.com/FWuermse/lean4-sql-utils" "main"
  }]
```

## Usage

Currently the main feature includes built in query syntax that can be used the following way:

```lean
import SqlUtils.SQLSyntax

def main : IO Unit := do
  let query :=
    SELECT name, age, height, job_name
    FROM person LEFT JOIN job ON person.job_id = job.id
    WHERE person.age > 20
  IO.println query
```

## Contributing

Contributions are always welcome. Please refer to the [Lean4 Contributing Guidelines](https://github.com/leanprover/lean4/blob/master/CONTRIBUTING.md) and their [commit convention](https://leanprover.github.io/lean4/doc/dev/commit_convention.html).
